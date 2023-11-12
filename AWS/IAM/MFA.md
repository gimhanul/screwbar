그룹과 사용자들의 정보가 침해당하지 않도록 보호해야 함.

# Password Policy
비밀번호 정책을 정의해 보안을 강화할 수 있음.
## Custom Options
- 비밀번호의 최소 길이 설정
- 특정 유형의 글자 사용 요구
	- 대소문자
	- 숫자
	- 특수문자
- 비밀번호 변경을 허용 / 금지
- 일정 기간이 지나면 비밃번호를 변경하도록 설정
- 이전에 사용했던 비밀번호를 사용하지 못하도록 설정

# MFA
다요소 인증. 필수적으로 사용하도록 권장함.
> 비밀번호와 보안 장치를 함꼐 사용하는 것.

## Device Options
- Virtual
	- Google Authenticator (phone only)
	- AUthy (multi-device)
- Universla 2nd Factor (U2F) Security Key
	- YubiKey by Yubico (3rd party)
- Hardware Key Fob
	- Provided by Gemalto (3rd party)
- Hardware Key Fob for AWS GovCloud (US)
	- Provided by SurePassId (3rd Party)