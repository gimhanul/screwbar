### 2-4-4. CsrfFilter

CsrfFilter는 `Csrf Attack을 방어`함.

<br>

**Csrf Attck**

악의적으로 페이지를 위조해서 정상 시스템에 악의적인 요청을 하는 것을 말함.

이를 방어하기 위해, Csrf Token을 사용함.

> 시스템에서 사용하는 정상적인 페이지는 올바른 csrf token을 갖고 요청을 할 수 있지만, 위조한 악의적인 페이지에는 본 시스템에서 사용하는 csrf token이 없기 때문에 틀린 csrf token으로 요청함.