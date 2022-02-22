### 2-4-8. ExceptionTranslationFilter

[FilterSecurityInterceptor](https://github.com/gimhanul/TIL/blob/master/Spring/Security/Filter/FilterSecurityInterceptor.md)에서 발생한 두 가지 Exception을 처리함.

- `AuthenticationException` : 인증 실패
- `AccessDeniedException`: 인가 실패

→ 인증이나 인가에 실패했을 때, 어떤 행동을 취할지 결정함.

<br>

**기본 설정**

다음 경우에는 login page로 이동함.
- AuthenticationException 발생
- Anonymous의 AccessDeniedException 발생

다음 경우에는 403 Frobidden Whitelabel Error Page로 이동함.
- 기명 User의 AccessDeniedException 발생