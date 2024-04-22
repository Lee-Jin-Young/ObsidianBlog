---
title: "[항해99 취업 리부트 코스 학습일지] 5주차"
description: "#항해99 #취리코 #취업리부트코스 #재취업 #중고신입 #스파르타코딩클럽 #개발자포트폴리오 #개발자이력서 #개발자취업 #개발자취준"
학습 기간: 2024-04-17 ~ 2024-04-23
bookCollapseSection: true
---
##### 이번 주의 개인 목표
- [ ] 시간 나면 코딩테스트 풀기

##### 이번 주의 항해 목표
- [ ] 1주차 Basic 완료 -> 환경 설정 및 보안관련 클래스 작성 완료


| 제목                                   | 작성일    |
| -------------------------------------- | --------- |
| [29일차](Hanghae99/5주차/29일차)     | 2024-04-17   |
| [30일차](Hanghae99/5주차/30일차) | 2024-04-18   |
| [31일차](Hanghae99/5주차/31일차)   | 2024-04-19 |
| [32일차](Hanghae99/5주차/32일차)   | 2024-04-20  |
| [34일차](Hanghae99/5주차/34일차)     | 2024-04-21  |
| [35일차](Hanghae99/5주차/35일차) | 2024-04-23  |

---
##### 다음 주의 개인 목표
- [ ] 북메이트 호스팅
- [ ] Velog로 학습일지 이전

##### 다음 주의 항해 목표
- [ ] 1,2주차 Basic 90%완료

---
#### 이번 주 항해 취업 리부트코스에서 내가 구현한 기능은 무엇인가요?
- 계층형 구조: 기존에 사용한 방식으로 각 계층별로 패키지를 구분하여 개발하는 방식.
- 도메인 구조: 각 도메인 별로 디렉터리를 나누어 관리하는 방식.

1. **계층형 구조의 장단점:**
    - 장점:
        - 전통적이고 익숙한 구조로 개발자들에게 친숙함.
        - 각 계층별로 역할이 명확히 구분되어 유지보수가 용이함.
    - 단점:
        - 도메인이 늘어날수록 패키지 구조가 복잡해질 수 있음.
        - MSA와 같이 도메인 별로 분리되는 아키텍처 전환 시에는 유연성 부족할 수 있음.

2. **도메인 구조의 장단점:**
    - 장점:
        - MSA와 같이 도메인 별로 분리되는 아키텍처 전환에 유리함.
        - 각 도메인별로 모듈화되어 재사용성이 높아짐.
    - 단점:
        - 처음에는 익숙하지 않을 수 있고, 변화에 대한 이해가 필요함.
        - 전통적인 계층형 구조에 비해 초기 설정과 구현이 조금 더 복잡할 수 있음.

- 결론
	- 추후 MSA로 변경 될 예정인 만큼 확장성을 위해 도메인 구조로 설계하기로 함


#### 이번 주 겪은 트러블 슈팅이 있다면 무엇인가요?
- 문제 발생
	- Postman에서 URI 요청 시에 상태 코드가 401(Unauthorized)로 반환되는 문제 발생
	- CORS(Cross-Origin Resource Sharing) 설정이 제대로 되어 있지 않아서 발생한 문제였다.

- 해결 방안
	- WebMvcConfigurer를 통한 설정과 Spring Security중 하나를 활용하여 설정
	- Spring Security가 추후 다른 보안 설정시에 조금 더 유리한 듯 하여 이를 활용하기로 함
	- 온전히 이해 하는 것은 어려워 일단 disable해 둔 후 추후에 다시 리팩토링 할 예정
``` java
@Configuration  
@EnableWebSecurity  
@RequiredArgsConstructor  
public class SecurityConfig {  
    @Bean  
    public SecurityFilterChain filterChain(HttpSecurity http) throws Exception {  
        http  
                .csrf((csrf) -> csrf.disable())  
                .authorizeHttpRequests(authorize -> authorize.anyRequest().permitAll()) // 모든 요청에 대해 인증 없이 접근 허용  
                .securityMatcher(new AntPathRequestMatcher("/**")); // 모든 경로에 대한 보안 매처 설정  
        return http.build();  
    }  
  
  
    @Bean  
    public CorsConfigurationSource corsConfigurationSource() {  
        CorsConfiguration configuration = new CorsConfiguration();  
  
        // 모든 출처 (*) 를 허용  
        configuration.addAllowedOriginPattern("*");  
        configuration.addAllowedHeader("*");  
        configuration.addAllowedMethod("*");  
        configuration.setAllowCredentials(false);  
  
        UrlBasedCorsConfigurationSource source = new UrlBasedCorsConfigurationSource();  
        source.registerCorsConfiguration("/**", configuration);  
  
        return source;  
    }  
```

#### Q.  이번 주 진행된 개인 프로젝트에서 얻은 인사이트는 무엇인가요?
- 테스트 코드등의 작성도 중요하다.

---
**항해99 취업 리부트 코스를 수강하고 작성한 콘텐츠 입니다.**

[https://hanghae99.spartacodingclub.kr/reboot](https://hanghae99.spartacodingclub.kr/reboot)

#개발자포트폴리오 #개발자이력서 #개발자취업 #개발자취준 #코딩테스트 #항해99 #취리코 #취업리부트코스 #재취업