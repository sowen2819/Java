# 객체지향 5대 원칙
 - SRP (The Single Responsibility Principle)
 - OCP (The Open Close Principle)
 - LSP (The Liskov Substitution Principle)
 - ISP (The Interface Segregation Principle)
 - DIP (The Dependency Inversion Principle)

# 필요한 조엘 테스트  

 1. 버전 관리시스템 ( git )  
 2. 빌드 자동화 ( Maven )  
 3. 버그 추적시스템을 운영하고 있습니까?   
 4. 일정을 업데이트하고 있습니까?  
 5. 명세서를 작성하고 있습니까?  
 6. 일일 빌드를 하고 있습니까?  


# Java 코딩 규칙

 - [구글 javaGuide](https://google.github.io/styleguide/javaguide.html)
 - [한글 Guide](https://myeonguni.tistory.com/1596)


# Java Test

 - 인스턴스 비교 ( hashCode 비교 => Equals 비교 ) 
 - 시간측정
 
<pre>
      long start = System.currentTimeMillis();  
      long end = System.currentTimeMillis();  
      long result = ( end - start ) / 1000.0;  
      System.out.println( "알고리즘 실행 시간 : " + result );  
</pre>
 
 
# JVM

 - TestJava.java, TestJava.class
 - java -cp "/lib/*" TestJava
 - java -jar testjava.jar TestClass args[0].properties
 - javac -d . TestJava.java
 - java -cp . 패키지.클래스명
  
  
 # Java Clean Code
 
- 클래스 이름( 명사, 명사구 )

- 메서드 이름( 동사, 동사구 )

- 블록과 들여쓰기
  - 1단 혹은 2단을 넘지마라!

- 명령과 조회를 분리하라
  - 뭔가를 수행하거나 반환하거나 둘 중 하나만 해라!
  - 오류처리도 한 가지 작업이다!
  
- 함수의 인수를 줄여라!

- 주석
  - 법적인 주석
  - 공식이나 정보를 제공하는 주석

- null을 전달, 반환하지 마라
  - null을 전달, 반환하는 함수는 null체크 때문에 코드를 더럽게 만든다.
  
- Log4j2 혹은 logback( Logger.log(e.getMessage))
- 변수명 정하기
  - 해법영역
  - 문제영역
  
- 적절한 행길이 유지
- 가로 형식 맞추기

# EFFECTIVE JAVA

 - 객체의 생성과 파괴
   1. Public 생성자 대신 정적 팩터리 메서드를 고려하라
   2. 생성자에 매개변수가 많다면 빌더를 고려하라
   3. private 생성자나 열거 타입으로 싱글턴임을 보증하라
   4. 인스턴스화를 막으려거든 private 생성자를 사용하라
   5. 자원을 직접 명시하지 말고 의존 객체 주입을 사용하라
   6. 불필요한 객체 생성을 피하라
   7. 다 쓴 객체 참조를 해제하라
   8. finalizer와 cleaner 사용을 피하라
   9. try-finally보다는 try-with-resources를 사용하라
   
 - 모든 객체의 공통 메서드    
   10. equals는 일반 규약을 지켜 재정의하라  
   11. equals를 재정의 하려거든 hashCode도 재정의하라  
   12. toString을 항상 재정의하라  
   13. clone 재정의는 주의해서 진행하라  
   14. Comparable을 구현할지 고려하라  

- 클래스와 인터페이스
   15. 클래스와 멤버의 접근 권한을 최소화하라  
   16. public 클래스에서는 public 필드가 아닌 접근자 메서드를 사용하라  
   17. 변경 가능성을 최소화하라  
   18. 상속보다는 컴포지션을 사용하라  
   19. 상속을 고려해 설계하고 문서화하라. 그리지 않았다면 상속을 금지하라.  
   20. 추상 클래스보다는 인터페이스를 우선하라.  
   21. 인터페이스는 구현하는 쪽을 생각해 설계하라.  
   22. 인터페이스는 타입을 정의하는 용도로만 사용하라.  
   23. 태그 달린 클래스보다는 클래스 계층구조를 활용하라.  
   24. 멤버 클래스는 되도록 static으로 만들라  
   25. 톱레벨 클래스는 한 파일에 하나만 담으라.  

- 제네릭  
   26. 로타입(raw Type)은 상용하지 말라.  
   27. 비검사 경고를 제거하라  
   28. 이왕이면 제네릭 타입으로 만들라  
   30. 이왕이면 제네릭 메서드로 만들라  
   31. 한정적 와일드카드를 사용해 API 유연성을 높이라  
   32. 제네릭과 가변인수를 함께 쓸 때는 신중하라  
   33. 타입 안전 이종 컨테이너를 고려하라.  
   
- 열거 타입과 애너테이션  
   34. int 상수 대신 열거 타입을 사용하라.    
   35. ordinal 메서드 대신 인스턴스 필드를 사용하라  
   36. 비트 필드 대신 EnumSet을 사용하라.  
   37. ordinal 인덱싱 대신 EnumMap을 사용하라.   
   38. 확장할 수 있는 열거 타입이 필요하면 인터페이스를 사용하라.  
   39. 명명 패턴보다 애너테이션을 사용하라.  
   40. @Override 애너테이션을 일관되게 사용하라  
   41. 정의하려는 것이 타입이라면 마커 인터페이스를 사용하라.  
   
- 람다와 스트림  
   42. 익명 클래스보다는 람다를 사용하라.  
   43. 람다보다는 메서드 참조를 사용하라.  
   44. 표준 함수형 인터페이스를 사용하라.  
   45. 스트림은 주의해서 사용하라.  
   46. 스트림에서는 부작용 없는 함수를 사용하라.  
   47. 반환 타입으로는 스트림보다 컬렉션이 낫다.  
   48. 스트림 병렬화는 주의해서 적용하라.  

- 메서드
   49. 매개변수가 유효한지 검사하라  
   50. 적시에 방어적 복사본을 만들라  
   51. 메서드 시그니처를 신중히 설계하라  
   52. 다중정의는 신중히 사용하라  
   53. 가변인수는 신중히 사용하라  
   54. null이 아닌, 빈컬렉션이나 배열을 반환하라  
   55. 옵셔널 반환은 신중히 하라  
   56. 공개된 API 요소에는 항상 문서화 주석을 작성하라  
   
# JDK
 - jdk6  
 - jdk7  
 - jdk8  
 
 # URL 주의 사항
  - 한글 파라미터로 값을 날릴때는 UTF-8로 인코딩을 한다.  
  - URLEncoder.encode("한글", "UTF-8");  

# Java 메모리 Leak
  - 시스템 자원을 사용하는 객체
  - 익명 클래스 혹은 내부 클래스의 객체
