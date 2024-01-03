## Refresh Token
```
JWT는 토큰 자체에 정보를 담고있어 보안이 매우 취약하다. 만약 JWT 토큰을 탈취당하게 되면 해당 사용자의 권한과 정보를 모두 빼앗기게 된다.
 
이를 보완하기 위해서 Refresh Token의 개념이 사용되었다.

Access Token의 유효기간은 매우 짧게
Refresh Token의 유효기간은 길게

해주는 것이 포인트이다.
 
즉,

Access Token을 통해서만 자원에 접근이 가능, But 유효기간이 매우 짧다(탈취를 당해도 이미 사용할 수 없는 상태)
Refresh Token은 유효기간이 길기에 탈취당할 수도 있지만 Refresh Token은 오직 Access 토큰을 재발급하는 용도(Refresh Token 자체로는 별 쓸모가 없다.)
출처: https://jangjjolkit.tistory.com/26 [장쫄깃 기술블로그:티스토리]
```