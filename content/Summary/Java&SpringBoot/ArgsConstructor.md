### `@RequiredArgsConstructor` &  `@AllArgsConstructor` 

### 공통점
- Lombok에서 제공하는 어노테이션
- 생성자를 자동으로 생성해주는 기능을 제공

### 차이점
1. **대상 필드 설정**
    - `@RequiredArgsConstructor`: 해당 필드에 **`final` 키워드가 붙어있는 필드**만을 대상으로 생성자를 생성
    - `@AllArgsConstructor`: 클래스의 **모든 필드**를 대상으로 생성자를 생성
2. **사용 시나리오**
    - `@RequiredArgsConstructor`
	    - 주로 불변(Immutable) 객체를 만들 때 사용
	    - 필드가 `final`로 선언되어 있어야 함
	    - 일반적으로 값이 변경되지 않는 경우에 사용
    - `@AllArgsConstructor`
	    - 모든 필드를 초기화하는 생성자를 필요로 할 때 사용
	    - 모든 필드가 초기화될 수 있어야 함
	    - 값이 변경될 수 있는 경우에 사용
    
``` java
import lombok.RequiredArgsConstructor;

@RequiredArgsConstructor 
public class RequiredArgsExample {
	private final String field1;     
	private final int field2; 
}  

```
- `@RequiredArgsConstructor` 어노테이션을 사용하여 생성자를 생성
- 이 클래스의 모든 필드는 `final`로 선언
	->`@RequiredArgsConstructor`는 이러한 필드만을 대상으로 생성자를 생성

``` java
import lombok.AllArgsConstructor;  

@AllArgsConstructor 
public class AllArgsExample {     
	private String field1;     
	private int field2; 
}
```
- `AllArgsExample` 클래스는 `@AllArgsConstructor` 어노테이션을 사용하여 생성자를 생성
- 이 클래스는 모든 필드를 대상으로 생성자를 생성
	-> `final`로 선언되지 않은 필드도 생성자에 포함