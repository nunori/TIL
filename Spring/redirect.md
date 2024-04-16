# return "redirect://index", return "/index" 차이
return `"redirect:/index"`는 HTTP 리디렉션을 사용한다. 이 방식에서 서버는 HTTP 상태코드 (302 FOUND or 303 See Other)와 함께 클라이언트에게 새로운 URL`("/index")`로의 리디렉션을 지시하는 HTTP 응답을 보낸다. 그 결과, 클라이언트의 브라우저는 지정된 새 URL로 자동으로 요청을 보내게 되고, 브라우저 주소창의 URL도 새로운 주소로 변경된다.<br>

리디렉션은 폼 제출 후 페이지를 새로고침할 때 발생할 수 있는 중복 제출 문제를 방지하는 데 유용하다.<br>

`return "/index"`는 사용자에게 직접 /index 페이지의 내용을 렌더링해서 보여준다. URL 변경 없이 서버에서 직접 페이지를 생성하여 반환한다.<br>

`return "redirect:/index"`는 사용자의 브라우저를 `/index` URL로 리디렉션하여, 브라우저가 새 URL에 대한 요청을 다시 보내도록 한다. 이 과정에서 URL이 변경된다.