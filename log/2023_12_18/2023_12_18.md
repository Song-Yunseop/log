## Qualifier
```
@Autowired를 통해 객체를 주입할 때 같은 타입의 객체가 여러 개 있다면, 구분할 수 없다. 이때 @Qualifier를 통해 식별자를 부여하면 원하는 객체를 주입받을 수 있다.

@Autowired @Qualifier("desktop")
Computer desktop;
	
@Autowired @Qualifier("laptop")
Computer laptop;

//@Primary를 써놓은곳은 디폴트가 된다.	
@Autowired
Computer computer;
```

```
데이터베이스 회원테이블, 게시판 테이블, 댓글 테이블 만들었다.
```