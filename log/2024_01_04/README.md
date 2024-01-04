##UserController
```
login 요청을 받는 메소드를 만들어줬다. 요청이 들어오면 username과 password를 서비스단의 login 메소드로 넘겨준다.
```

##UserService
```
login요청이 들어오면 같이 온 유저 정보 email, password로 인증 과정을 진행한다.
Username과 Password 기반의 Authentication Token 객체를 생성해
검증 과정을 진행한다.
그리고 그 검증된 인증 정보로 JWT 토큰을 생성한다.
```
