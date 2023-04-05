# dev-book
<h2>2.1 WAS, 웹 서버, 서블릿의 역할</h2>
-서블릿은 컨테이너라는 자바 애플리케이션의 지배를 받는다.
<br><br>
톰캣은 컨테이너의 대표적인 예로, 아파치와 같은 웹 서버가 사용자로부터 서블릿에 대한 요청을 받으면 이를 서블릿이 배포된 컨테이너가 받아 HTTP Request, HTTP Response 객체를 매개로 서블릿의  doPost() 또는 doGet() 메소드를 호출한다.  
<br><br>
**컨테이너의 역할
1. 서블릿과 웹 서버가 통신할 수 있도록 지원
2. 서블릿의 생명주기 관리
3. 멀티스레딩 지원
4. DD(배포서술자)를 이용한 보안관리 가능
5. JSP 지원
<h2>2.2 서블릿의 3가지 이름과 배포 서술자 </h2>
서블릿은 사용자에 따라 3가지 각기 다른 명칭을 가질 수 있다. <br>
1. 클라이언트가 아는 URL 이름 ex>register/registerMe<br>
2. 배포자가 만든 내부적인 이름<br>
3. 개발자가 만든 실제 파일명 ex>classes/registration/SignUpServelet.class(클래스명과 패키지 명을 포함)
<br>
위의 3가지 이름을 이용해 배포 서술자에서 서블릿을 매핑시킬 수 있다.
<br>
(servelet)<br>
    (servelet-naem)내부이름 작성(/servelet-naem)<br>
    (servelet-class)개발자 이름 작성(/servelet-class)<br>
(/servelet)
(servelet-mapping)<br>
    (servelet-naem)내부이름 작성(/servelet-naem)<br>
    (url-pattern)URL 이름(/url-pattern)<br>
(/servelet-mapping)
<br><br>
<h2>2.3 서블릿과 JSP, MVC 디자인패턴 </h2>
초창기 서블릿: 뷰와 비즈니스 로직이 혼재되어 있는 형태, 한 페이지 안에서 요청을 받아 비즈니스 로직을 실행시키고, 뷰 코드를 읽어 화면에 표출한다. 기능적으로 서블릿을 각기 다르게 생성해 비즈니스 로직을 분리시킬 수는 있었음
<br><br>
JSP: 비즈니스 로직 부분을 서블릿이 담당하고, HTML과 관련한 프레젠테이션 부분을 JSP에서 처리하도록 해.뷰와 서블릿을 부분을 분리하여 사용
<br><br>
MVC 디자인 패턴:의존성을 낮추고, 재사용성을 높이기 위해 고안된 디자인 패턴<br>
Model: 비즈니스 로직이 들어가는 부분, DB와 통신하는 유일한 곳<br>
View: 사용자가 입력한 정보를 컨트롤러에게 전달하고, 컨트롤러부터 모델 정보를 읽어온다. 프레젠테이션 부분을 담당.<br>
Controller: Request 객체에서 사용자가 입력한 정보를 뽑아내어 모델에 대해 어떤 작업을 해야하는지 알아내는 역할을 한다. 




