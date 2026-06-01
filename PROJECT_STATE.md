# SBX Mail Signature Test - Project State

## 현재 상태

- Google Sites 테스트용 HTML과 Gmail 서명용 HTML을 분리했다.
- 두 HTML 모두 `table + inline style` 중심 구조로 정리했다.
- 깨져 있던 한글 문구를 UTF-8 기준으로 다시 작성했다.
- 개인정보 고지문은 유지했다.
- 신규 로고 파일은 `assets/` 폴더에 있다.
- 로고 공개 HTTPS URL은 GitHub Raw URL을 사용한다.

## 로고 공개 HTTPS URL

```text
https://raw.githubusercontent.com/jhchoi-blip/-mail/main/assets/SBX_horizontal_bk_400.png
```

확인 결과 위 URL은 `200 OK`로 응답하며 `Content-Type: image/png`를 반환한다.

장기 운영에는 회사 CDN, S3/CloudFront, 웹 서버, 공개 이미지 호스팅처럼 캐시와 권한 정책을 직접 관리할 수 있는 URL이 더 안정적이다. Google Drive 공유 링크는 이미지 파일의 직접 URL이 아니거나 권한/리다이렉트 이슈가 생길 수 있어 Gmail 서명용으로는 권장하지 않는다.

## 생성/수정 파일

- `google-sites-template.html`
  - Google Sites `삽입 > 코드 삽입 > 소스 코드` 테스트용 템플릿
  - 로고 URL 적용 완료
- `google-sites-copy-this-final.html`
  - Google Sites에 그대로 붙여넣기 위한 최종본
- `gmail-signature-template.html`
  - Gmail 서명 확인용 전체 HTML 템플릿
  - Gmail에는 내부 `<table>...</table>` 영역을 붙여넣는다.
- `gmail-signature-copy-this.html`
  - Gmail 서명 입력란에 바로 붙여넣기 위한 table-only 최종본
- `assets/SBX_horizontal_bk.png`
  - 신규 로고 원본 복사본
- `assets/SBX_horizontal_bk_400.png`
  - 서명 표시용 400px 로고

## 남은 확인 사항

- Google Sites 테스트 페이지에 `google-sites-copy-this-final.html` 내용을 붙여넣어 실제 표시를 확인한다.
- Gmail 서명 입력란에 `gmail-signature-copy-this.html` 내용을 붙여넣어 로고와 한글 표시를 확인한다.
- 최종 운영 전 이름, 직책, 연락처, 이메일 주소를 실제 사용자 정보로 교체한다.
