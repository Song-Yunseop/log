-csrf().disable()
```
csrf(cross site request forgery) : 사이트간 위조 요청
인증된 사용자의 토큰을 탈취해 위조된 요청을 보냈을 경우 파악해 방지하는 것
```

disable 이유?
```
rest api 에서는 권한이 필요한 요청 위해서 인증 정보를 포함시켜야 함
서버에 인증정보 저장하지 않기 때문에 작성할 필요 없음
(JWT를 쿠키에 저장하지 않기 때문)
```

-sessionManagement().sessionCreationPolicy(SessionCreationPolicy.STATELESS)
```
JWT를 사용하기 때문에 세션도 사용하지 않는다.
```

-formLogin().disable() & httpBasic().disable()
```
HTTP Basic Authentication과 Form Based Authentication을 사용하지 않는다.
```

-antMatchers("/api/user").permitAll()
```
해당 요청에 관해 모두 접근가능하게 한다.
```

-addFilterBefore(new JwtAuthenticationFilter(jwtTokenProvider), UsernamePasswordAuthenticationFilter.class)
```
UsernamePasswordAuthenticationFilter에 가기 전에 직접 만든 JwtAuthenticationFilter을 실행하겠다.
```