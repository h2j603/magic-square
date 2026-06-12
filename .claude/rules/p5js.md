---
paths:
  - "**/*.html"
  - "**/artworks/**"
  - "**/canvas/**"
---

# p5.js 작업 규칙

## 필수 구조

```javascript
// 인스턴스 모드 (Next.js 프로젝트)
const sketch = (p) => {
  p.setup = () => { ... }
  p.draw = () => { ... }
  p.windowResized = () => {
    p.resizeCanvas(p.windowWidth, p.windowHeight)
  }
}

// 독립 HTML
function setup() { createCanvas(1080, 1080) }
function windowResized() {
  let s = min(windowWidth, windowHeight)
  resizeCanvas(s, s)
}
function keyPressed() {
  if (key === 's') saveCanvas('artwork', 'png')
  if (key === 'r') { clear(); redraw() }
}
```

## 색상

- HSB 모드 권장: `colorMode(HSB, 360, 100, 100, 100)`
- 팔레트는 변수로 선언 후 재사용
- 투명도는 4번째 인자 (0-100)
- 변환이 필요하면 `color` MCP 사용

## 성능

- `draw()` 안에서 객체 생성 피하기 → `setup()`에서 미리 초기화
- 정적 작품: `noLoop()` 후 `redraw()` 패턴
- 많은 요소: `pg = createGraphics()` 오프스크린 버퍼 활용

## 저장 경로

- 독립 HTML: `~/workspace/artworks/YYYY-MM-DD_제목.html`
- Next.js 컴포넌트: `~/workspace/experiments/` 하위

## 금지

- `p5.js` v2 기능 혼용 (CDN은 1.11.3 고정)
- `angle` 없이 `rotate()` 호출
- `push()`/`pop()` 없이 변환(translate/rotate/scale) 사용
