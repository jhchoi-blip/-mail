# SBX Mail Signature Test

## 목적

Google Sites 테스트 페이지와 Gmail 서명 설정에 넣어볼 수 있는 테스트용 메일 서명 HTML입니다.

## 파일

- `google-sites-template.html`: Google Sites `삽입 > 코드 삽입`용 템플릿입니다.
- `gmail-signature-template.html`: Gmail 서명 입력란에 복사하기 위한 템플릿입니다.
- `assets/SBX_horizontal_bk.png`: 첨부받은 신규 로고의 작업용 복사본입니다.

## 사용 방법

1. 로고를 공개 접근 가능한 `https://` URL로 업로드합니다.
2. `gmail-signature-template.html`과 `google-sites-template.html`의 `LOGO_IMAGE_URL`을 실제 로고 URL로 교체합니다.
3. Google Sites 테스트 페이지에는 `google-sites-template.html` 전체를 코드 삽입에 넣어 확인합니다.
4. Gmail 서명 입력란에는 `gmail-signature-template.html`의 `<table>...</table>` 부분을 복사해 붙여넣습니다.

## 확인 필요

- Gmail과 Google Sites 테스트 모두 로컬 파일 경로와 `data:` 이미지 URI 대신 공개 `https://` 이미지 URL 사용을 권장합니다.
- 실제 운영 적용 전에는 신규 로고를 공개 `https://` URL로 호스팅해야 합니다.
