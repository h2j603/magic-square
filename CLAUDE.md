# CLAUDE.md — artworks (p5.js 제너레이티브 아트)

> 클라우드/로컬 세션 공통 컨텍스트.

## 프로젝트

p5.js 제너레이티브 아트 모음. **작품 1개 = 단일 HTML 파일** (CDN 로드, 빌드 없음).

- 현재 작품: `magic-square.html` — 한자 마방진 (리포명 magic-square)
- 새 작품 파일명: `YYYY-MM-DD_제목.html` 또는 `제목.html` (영문 케밥 케이스)

## p5.js 컨벤션

- CDN 고정: `https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.11.3/p5.min.js` (v2 기능 금지)
- 캔버스 기본 1080×1080 (SNS) 또는 A4 비율, `windowResized()` 필수
- `keyPressed()`: 's' = `saveCanvas()`, 'r' = 재생성
- HSB 모드 권장, 팔레트는 변수 선언 후 재사용
- `draw()` 안 객체 생성 금지, 정적 작품은 `noLoop()` + `redraw()`
- 변환(translate/rotate/scale)은 `push()`/`pop()`으로 감싸기
- 상세 → `.claude/rules/p5js.md`

## 전역 규칙

- 대화·커밋 메시지·코드 주석 모두 **한국어**. 커밋은 명령형.
- 작업은 feature 브랜치 → `main` PR 생성 → 머지까지 완료.
- 한글 폰트: Pretendard, Noto Sans KR (Google Fonts CDN)
