# MEME BOX.zip 🎁

2020~2026 연도별 밈을 선택해 친구에게 '선물' 링크를 보내는 정적 웹 앱입니다. 사이트 설치나 회원가입은 필요 없습니다.

## 구현된 것

- 2019~2026년 밈 **35개** 수록, 검색 및 연도별 필터
- 최신 릴스 / 브레인롯 / 근본 밈 / 랜덤 프리셋
- 여러 밈 선택, 받는 사람 이름, 마지막 한마디, 킹받음 강도 1~5
- 선물 개봉 애니메이션, 효과음(Web Audio), 브라우저 TTS(지원 시), 자동 진행/건너뛰기
- 미리보기, 공유 링크 생성, 복사 및 모바일 공유 메뉴
- URL 해시(`/#gift/…`)로 설정 직렬화 → 서버 없이도 공유 가능
- 모바일 반응형, Escape 종료, 음소거, reduced-motion 선호 대응
- 방문 추적/외부 API/DB 없음. 콘텐츠는 사용자 기기에 남고 공유 링크에 설정값이 포함됩니다.

### 제한사항

**이 프로젝트에 원본 밈 영상·사진·음원은 포함되지 않습니다.** 상업적 이용, 재배포 허가 여부가 불확실하여 밈 이름과 자체 제작한 패러디 일러스트/브라우저 효과음을 사용합니다. 따라서 실제 릴스와 완전히 같은 보이스·안무를 재생하는 버전은 아닙니다. 추가하려면 권리를 확보한 오디오/영상 또는 직접 제작한 파일을 넣어야 합니다.

'최신' 밈은 2026-10-25 작성 시점의 샘플입니다. 자동 크롤링·SNS 연동은 포함되지 않습니다. 새 밈은 `app.js`에 객체를 추가하면 됩니다.

## 바로 실행

ES module 사용으로 `index.html`을 파일로 직접 열면 브라우저에 따라 스크립트가 차단됩니다. 폴더에서 아래 중 하나로 실행하세요.

```bash
python -m http.server 8000
# 브라우저: http://localhost:8000
```

## GitHub Pages 배포 (별도 반복 Actions 워크플로 없음)

1. GitHub에서 새 **Public repository** `meme-box` 생성. README 없이 빈 저장소 권장.
2. 이 폴더의 `index.html`, `styles.css`, `app.js`, `assets/favicon.svg`, `README.md`, `.nojekyll` 파일을 저장소 `main` 브랜치 루트에 업로드.
3. Repository → **Settings → Pages → Build and deployment** 에서 **Deploy from a branch** 선택.
4. Branch를 `main`, Folder를 `/(root)` 로 선택 후 Save.
5. 게시되면 `https://<YOUR_USERNAME>.github.io/meme-box/` 주소로 접속합니다. 게시 반영에는 GitHub 환경에 따른 지연이 발생할 수 있습니다.

이 저장소에는 매일/매시간 실행되는 Actions 워크플로를 추가하지 않습니다. GitHub Pages 배포 자체에는 GitHub 내부 배포 절차가 사용되므로 계정의 요금·사용량·Pages 정책은 별도로 확인하세요.

## 기술/프라이버시

- HTML, CSS, JavaScript (ES modules), 외부 npm 의존성 0개
- 폰트는 Google Fonts에서 로드하며, 외부 요청을 없애려면 `styles.css`의 `@import`를 삭제하고 시스템 폰트로 대체하세요.
- 링크 속 사람 이름과 메시지는 **암호화되지 않고 인코딩**된 내용입니다. 민감한 정보나 실명을 넣지 않는 것이 좋습니다.
- URL을 보유한 사람은 누구나 내용을 볼 수 있습니다. URL을 바꾸지 않고 선택값을 업데이트할 수는 없습니다.
- 원본 https://box.cyhuh.com/ 과 무관한 별도의 창작 프로젝트입니다.