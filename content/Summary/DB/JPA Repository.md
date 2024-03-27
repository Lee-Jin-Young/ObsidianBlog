`findAll()`, `findAllByID()`

`saveAll()`

`getOne()`, `findById()`

`flush()`, `saveAndFlush()`

---
##### 기존 북메이트 활동내역 쿼리
**Dto**
```java
@Data
@Builder
@NoArgsConstructor
@AllArgsConstructor
@Alias("usersInfoDto")
public class UsersInfoDto {
	private int num;
	private String group_name;
	private String writer;
	private String title;
	private String regdate;
	private String content;
	private int group_num;
	private int comu_num;
	private int cs_num;
	private int startRowNum;
	private int endRowNum;
	private int prevNum; //이전글의 글번호
	private int nextNum; //다음글의 글번호
}
```

**Controller**
```java
@Controller
public class UsersInfoController {
	@Autowired
	private UsersInfoService service;
	
	//작성 글 보기
	@GetMapping("/users/info/writing_list")
	public String WritingList(Model model) {
		service.getWritingList(model);
		return "users/info/writing_list";
	}

}
```

**Service**
```java
@Service
public class UsersInfoServiceImpl implements UsersInfoService {
	
	@Autowired
	private UsersInfoDao infoDao;
	@Autowired
	private InquireDao supportDao;
	
	@Override
	public void getWritingList(Model model) {
		HttpServletRequest request = ((ServletRequestAttributes) RequestContextHolder.getRequestAttributes()).getRequest();
		final int PAGE_ROW_COUNT = 5;
		final int PAGE_DISPLAY_COUNT = 5;
		
		String id = request.getSession().getAttribute("id").toString();

		int pageNum = 1;
		
		String strPageNum = request.getParameter("pageNum");
		if(strPageNum != null) {
			pageNum = Integer.parseInt(strPageNum);
		}
	
		int startRowNum = 1 + (pageNum-1) * PAGE_ROW_COUNT;
		int endRowNum = pageNum * PAGE_ROW_COUNT;
		
		UsersInfoDto dto = new UsersInfoDto();
		dto.setStartRowNum(startRowNum);
		dto.setEndRowNum(endRowNum);
		dto.setWriter(id);
		
		List<UsersInfoDto> list = infoDao.getWritingList(dto);
		
		int totalRow = infoDao.getWCount(dto);
		int startPageNum = 1 + ((pageNum - 1) / PAGE_DISPLAY_COUNT) * PAGE_DISPLAY_COUNT;
		int endPageNum = startPageNum + PAGE_DISPLAY_COUNT - 1;
		
		int totalPageCount = (int) Math.ceil(totalRow / (double) PAGE_ROW_COUNT);
		if (endPageNum > totalPageCount) {
			endPageNum = totalPageCount;
		}
		
		model.addAttribute("list", list);
		model.addAttribute("pageNum", pageNum);
		model.addAttribute("startPageNum", startPageNum);
		model.addAttribute("endPageNum", endPageNum);
		model.addAttribute("totalPageCount", totalPageCount);
		model.addAttribute("totalRow", totalRow);
		
	}
}
```

**Dao**
```java
@Repository

public class UsersInfoDaoImpl implements UsersInfoDao {

	@Autowired
	private SqlSession session;
	
	@Override
	public List<UsersInfoDto> getWritingList(UsersInfoDto dto) {
		return session.selectList("info.getWritingList", dto);
	}
}
```

**Mapper**
``` xml
<mapper namespace="info">
	<select id="getWritingList" parameterType="usersInfoDto" resultType="usersInfoDto">
	SELECT cb.comu_num AS num, cb.writer, cb.title, cb.regdate, cb.group_num, gt.name AS group_name
	FROM (
		SELECT result1.*, ROWNUM AS rnum
		FROM (
			SELECT comu_num, writer, title, regdate, group_num
			FROM community_board_tb
			WHERE writer = #{writer}
			ORDER BY comu_num DESC
		) result1
	) cb
	LEFT JOIN group_tb gt ON cb.group_num = gt.num
	<![CDATA[
	WHERE cb.rnum >= #{startRowNum} AND cb.rnum <= #{endRowNum}
	]]>
	</select>
</mapper>
```

---
##### JPARepasitory, Entity, Vo 활용 쿼리
**Dto**
```java
@Data
@NoArgsConstructor
@AllArgsConstructor
public class WritingDto {
	Integer id_writing;
	String title;
	Integer group_id;
	LocalDateTime regdate;
}
```

**Entity**
```java
@Entity  
@NoArgsConstructor  
@AllArgsConstructor  
@Builder(toBuilder = true)  
@ToString  
@Data  
@Table(name = "community_board_tb", schema = "bookmate")
public class CommunityBoard {
	@Id
	@Column(name = "id_writing)
	Integer id_writing;

	@Column(name = "user_id" nullable = false)
	String writer;

	@Column(name = "group_id" nullable = false)
	int group_num;

	@Column(name = "")
	String title;
	
	String regdate;
	
	String content;

	int comu_num;
	int cs_num;
	int startRowNum;
	int endRowNum;
	int prevNum; //이전글의 글번호
	int nextNum; //다음글의 글번호
}
```

**Vo**


**Controller**
```java
@Controller
public class UserController {
	@GetMapping("/activity/writing_list")
	public ResponseEntity<?> getWritingList( @RequestParam 
	) {
		Object object =  userActivityService.getWritingList(
				id, page, size)
		SuccessResponse response = new SuccessResponse(SuccessCode.SELECT_SUCCESS, object);  
		return new ResponseEntity<>(response, HttpStatus.OK);
	}

}
```

**Service**
```java
@Service  
@AllArgsConstructor  
public class userActivityService {
	public Object getWritingList(Integer membId, Integer page, Integer size) {  
	JSONObject jsonObject = new JSONObject();
	Pageable pageable = PageRequest.of(page, size);
	
	Page<WritingDto> dtoList = membActivityRepository.getWritingListBymembId(membId, pageable);
	
	jsonObject.put("dtoList", dtoList);
	
	return jsonObject;  
	}
}
```

**Repository**
```java
public interface membActivityRepository extends JpaRepository<WritingDto, String> {
	@Query()
	
	Page<WritingDto> getWritingListBymembId(Integer membId, Pageble pageable);
}
```

---
##### 차이점
1. 페이징 처리
	- 기존 쿼리의 경우 페이징 처리를 위해 행번호를 새로 부여 하여 새로운 뷰를 생성
	- Service부분의 페이징처리 알고리즘을 JPA의 page 인터페이스로 대체 하여 사용
		- Service의 코드감소
		- 이동하는 정보의 양 감소
	-




https://m.blog.naver.com/hj_kim97/222780110215