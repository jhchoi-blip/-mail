# SBX Mail Signature Test - Project State

## 현재 상태

- 기존 Google Sites 메일 서명 HTML을 바탕으로 테스트용 서명 템플릿을 정리했다.
- Google Sites용 HTML과 Gmail 서명용 HTML을 분리했다.
- 한글 깨짐 문제를 확인했고, UTF-8 기준으로 파일을 재생성했다.
- 개인정보 고지문은 원문을 유지했다.
- 첨부 로고 `SBX_가로_bk.png`는 로컬 작업 폴더의 `assets/` 아래에 복사해두었다.

## 완료한 일

- `table + inline style` 중심으로 Gmail 복붙 호환 구조를 작성했다.
- `style` 태그와 class 의존을 제거했다.
- Google Sites 소스 코드 삽입용 템플릿을 만들었다.
- Gmail 서명 입력란용 템플릿을 만들었다.
- Google Sites 테스트를 위해 base64 로고 포함 버전도 만들었으나, Google Sites에서 `data:image`가 안정적으로 렌더링되지 않는 문제가 있었다.

## 생성/수정한 파일

- `google-sites-template.html`
  - Google Sites `삽입 > 코드 삽입 > 소스 코드`용 템플릿
  - `LOGO_IMAGE_URL`을 공개 HTTPS 이미지 URL로 교체해야 한다.
- `gmail-signature-template.html`
  - Gmail 서명용 템플릿
  - Gmail 입력란에는 내부 `<table>...</table>` 영역을 복사해서 사용한다.
- `google-sites-copy-this-test.html`
  - 원본 로고 base64 포함 테스트 파일
  - Google Sites에서 정상 렌더링되지 않을 수 있다.
- `google-sites-copy-this-test-small.html`
  - 400px로 줄인 로고 base64 포함 테스트 파일
  - Google Sites에서 정상 렌더링되지 않을 수 있다.
- `assets/SBX_horizontal_bk.png`
  - 첨부받은 신규 로고 원본 복사본
- `assets/SBX_horizontal_bk_400.png`
  - Google Sites 테스트용으로 축소한 로고

## 결정 사항

- 운영 Google Sites 페이지는 아직 수정하지 않는다.
- 최종 운영/테스트용 HTML은 `LOGO_IMAGE_URL` 방식이 맞다.
- 로고가 실제로 보이려면 공개 접근 가능한 `https://...png` 이미지 URL이 필요하다.

## 남은 리스크

- Google Sites는 로컬 파일 경로를 읽을 수 없다.
- Google Sites는 `data:image/png;base64,...` 이미지를 차단하거나 렌더링하지 않을 수 있다.
- Gmail도 base64 이미지나 로컬 파일 경로를 안정적으로 지원하지 않는다.
- 따라서 최종 테스트에는 신규 로고의 공개 HTTPS URL이 필요하다.

## 다음 액션

1. `SBX_가로_bk.png`를 Google Drive, S3, 회사 CDN, 웹 서버 중 하나에 업로드한다.
2. 외부에서 접근 가능한 공개 HTTPS 이미지 URL을 확보한다.
3. `google-sites-template.html`과 `gmail-signature-template.html`의 `LOGO_IMAGE_URL`을 실제 URL로 교체한다.
4. Google Sites 테스트 페이지에는 `소스 코드` 탭에 HTML을 붙여넣는다.
5. Gmail은 템플릿의 `<table>...</table>` 영역을 서명 입력란에 붙여넣어 테스트한다.

## 확인 필요

- 신규 로고를 어디에 호스팅할지 결정 필요
- Google Sites 테스트 페이지에 삽입할 최종 문구/개인 정보 확정 필요
- Gmail 실제 적용 전 수신 테스트 필요
