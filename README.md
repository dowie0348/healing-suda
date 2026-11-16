# healing-suda (우리 반 힐링수다날)

3학년 1반 '힐링수다날' 추천 앱입니다. GitHub Pages로 `index.html`이 그대로 배포됩니다.

## 보안 메모 (2026-11-17 정리)

- 앱은 Firebase Realtime Database(`healing-263grade1-default-rtdb`)에 추천 횟수를 저장합니다.
- 보안 규칙 사본: `database.rules.json` (실제 적용은 Firebase 콘솔 > Realtime Database > 규칙에서 합니다.
  이 파일은 GitHub Pages로 배포되지 않습니다.)
- 규칙 요약: 읽기는 누구나(수업용 공개 페이지), 쓰기는 `healingData/<연월>/<항목>/<학생>` 경로에
  "0 또는 1로 새로 만들기"와 "현재 값 +1"만 허용. 전체 덮어쓰기·삭제·임의 값 입력은 차단됩니다.
- 교사 메뉴 비밀번호는 소스에 평문으로 두지 않고 SHA-256 해시로만 비교합니다.
  비밀번호를 바꾸려면 새 비밀번호의 SHA-256 값을 구해 `TEACHER_PW_SHA256` 상수를 바꾸면 됩니다.
