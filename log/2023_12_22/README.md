### controller
```
@Controller
@RequestMapping("/board/**")
public class boardController {

	@GetMapping("/board")
	public String getboard() {
		return "/board/board";
	}

}

@Controller 어노테이션으로 컨트롤러의 역할을 수행하는 클래스란 것을 명시
@RequestMapping 어노테이션으로 "/board/"로 접근하는 url의 처리를 BoardController에서 맡는다고 명시
GetMapping("/board")를 통해 url 설정 즉 RequestMapping으로 설정한 /board, GetMapping으로 설정한 board로 접근하면 getboard()라는 메소드가 실행

반환형은 String으로, 반환 값은 "/board/board"로 되어있는데 이는 applicationProperties에서  thymeleaf.prefix로 설정한 ~~~/temaplate/ board/ board.html인 아까 위에서 작성한 board.html을 view로서 보여주게 됩니다. 
```