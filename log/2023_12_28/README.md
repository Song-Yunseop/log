```
오늘은 로그인을 구현하는데
<form th:action="@{/user/login}" autocomplete="off" method="POST">
이 부분에서 에러는 안뜨고 그냥 submit 버튼이 먹통이길래 시간을 많이 잡아 먹었다.
<form th:action="@{/user/login}" method="POST">
이렇게 autocomplete="off" 을 없애니 잘 작동된다!

```