## -목표

###### 자바가 제공하는 다양한 연산자를 학습하세요.



## 학습할 것

- package 키워드
- import 키워드
- 클래스패스
- CLASSPATH 환경변수
- -classpath 옵션
- 접근지시자



## 학습 내용 정리

#### - package 키워드

> * package
>
>   * 클래스의 묶음
>   * 패키지에는 클래스 또는 인터페이스를 포함시킬 수 있으며, 서로 관련된 클래스들끼리 그룹 단위로 묶어 놓음으로써 클래스를 효율적으로 관리할 수 있다.
>   * 같은 이름의 클래스 일지라도 서로 다른 패키지에 존재하는 것이 가능하므로, 자신만의 패키지 체계를 유지함으로써 다른 개발자가 개발한 클래스 라이브러리의 클래스와 이름이 충돌하는 것을 피할 수 있다.
>   * **클래스가 물리적으로 하나의 클래스파일(.class)인 것과 같이 패키지는 물리적으로 하나의 디렉토리이다.**
>   * 하나의 소스파일에는 첫 번째 문장으로 단 한 번의 패키지 선언만을 허용
>   * 모든 클래스는 반드시 하나의 패키지에 속해야 한다.
>   * 패키지는 점(.)을 구분자로 하여 계층구조로 구성할 수 있다.
>   * 패키지는 물리적으로 클래스 파일(.class)을 포함하는 하나의 디렉토리이다.
>
> * 패키지의 선언
>
>   ```java
>   package 패키지명;
>   ```
>



#### - import 키워드

> * import 문
>
>   * 클래스 코드를 작성하기 전에 import문으로 사용하고자 하는 클래스의 패키지를 미리 명시해주면 소스코드에 사용되는 클래스이름에서 **패키지명은 생략 할 수 있다.**
>   * import문의 역할은 컴파일러에게 소스파일에 사용된 클래스의 패키지에 대한 정보를 제공하는 것이다.
>   * 컴파일 시 컴파일러는 import문을 통해 소스파일에 사용된 클래스들의 패키지를 알아 낸 다음, 모든 클래스 이름 앞에 패키지명을 붙여준다.
>
> * import 문의 선언
>
>   > 일반적인 소스파일(.java)의 구성은 다음의 순서로 되어있다.
>   >
>   > 1. package 문
>   > 2. import 문
>   > 3. 클래스 선언
>
>   import문 선언하는 방법
>
>   > import 패키지명.클래스명;
>   >
>   > ​            또는
>   >
>   > import 패키지명.*;
>   >
>   > // 실행시 성능상의 차이는 전혀 없다.
>
> * static import 문
>   * static 멤버를 호출할 때 클래스 이름을 생햑할 수 있다.
>   * 특정 클래스의 static멤버를 자주 사용할 때 편리하며 코드도 간결해진다.



#### - 클래스패스

> * Class Path
>
>   * 클래스를 찾기위한 경로. 즉 JVM이 프로그램을 실행할 때, 클래스파일을 찾는 데 기준이 되는 파일 경로이다.
>
>   >- /export/home/username/java/classes와 같은 디렉토리
>   >- myclasses.zip과 같은 zip 파일
>   >- myclasses.jar와 같은 jar(자바 아카이브) 파일



#### - CLASSPATH 환경변수

> * 환경변수(Environment variable)
>
>   * 프로세스가 컴퓨터에서 동작하는 방식에 영향을 미치는 동적인 값들이다.
>
>     > 내 pc > 속성 > 고급 시스템 설정 > 고급 > 환경변수 > [새로만들기] 를 클릭해 직접 환경변수를 지정할 수 있다.



#### - -classpath 옵션

> *  java runtime에 -classpath 플래그를 사용해 환경변수를 지정할 수 있다.
>
> ```
> java -classpath ~
> java -cp
> ```
>
> -cp 혹은 -classpath : 클래스 패스를 지정할 때 사용하며, 이 옵션의 공백 뒤에 경로를 연달아 지정하면 된다.



#### - 접근지시자

> * access modifier(접근 제어자)
>
>   * 접근 제어자는 멤버 또는 클래스에 사용되어, 해당하는 멤버 또는 클래스를 외부에서 접근하지 못하도록 제안하는 역할을 한다.
>
>   * 접근 제어자는 default임을 알리기 위해 실제로 default를 붙이지는 않는다.
>
>   * 클래스나 멤버변수, 메서드, 생성자에 접근 제어자가 지정되어 있지 않다면, 접근 제어자가 default 임을 뜻한다.
>
>     >**접근 제어자가 사용될 수 있는 곳 - 클래스, 멤버변수, 메서드, 생성자**
>     >
>     >**private**  - 같은 클래스 내에서만 접근이 가능
>     >
>     >**default** - 같은 클래스 내에서만 접근 가능
>     >
>     >**protected** - 같은 패키지 내에서, 그리고 다른 패키지의 자손클래스에서 접근이 가능
>     >
>     >**public** - 접근 제한이 전혀 없다.
>
>     > 접근 범위가 넓은 쪽에서 좁은 쪽으로 나타내면 다음과 같다
>     >
>     > **public > protected > (default) > private**
>
>     | 대상     | 사용가능한 접근 제어자                |
>     | -------- | ------------------------------------- |
>     | 클래스   | public, (default)                     |
>     | 메서드   | public, protected, (default), private |
>     | 멤버변수 | public, protected, (default), private |
>     | 지역변수 | 없음                                  |




전체 출처: 자바를 다루는 기술, 자바의 정석