# Design Guide
## `2026 미래 성장 산업 & 주식 투자 리서치`

## 1. Design Philosophy

단일 HTML 파일로 배포되는 다크 테마 리서치 대시보드다. 기존 `product-designer-outlook-2026.html`의 톤을 계승해 어두운 배경, 보라/민트/앰버 포인트, 카드형 통계, 비교 테이블, 수평 바 차트, 출처 링크를 핵심 시각 언어로 사용한다.

외부 CSS/JS 라이브러리는 사용하지 않는다. 모든 스타일은 `index.html` 내부 `<style>` 블록에 포함하며, 색상은 CSS Custom Properties로 관리한다.

## 2. Color System

```css
:root {
  --bg: #0f0f13;
  --surface: #16161d;
  --surface2: #1e1e28;
  --surface3: #232331;
  --border: #2a2a38;
  --accent: #7c6ef7;
  --accent2: #56cfb2;
  --accent3: #f7a24b;
  --warn: #f76b6b;
  --blue: #63a7ff;
  --text: #e8e8f0;
  --text-muted: #9a9aaa;
  --text-dim: #626276;
}
```

## 3. Component Rules

| 컴포넌트 | 용도 |
|---|---|
| `.hero` | 리포트 제목, 기준일, 용도, 면책 문구 |
| `.stat-grid` / `.stat-card` | 시장 규모, CAGR, 거시 지표 등 핵심 숫자 |
| `.insight-grid` / `.insight-card` | 기업·테마별 정성 분석 |
| `.table-wrap table` | 산업별 전망, 밸류에이션, 투자자 유형 비교 |
| `.bar-section` | 관찰 지표 중요도 또는 상대 순위 |
| `.risk-grid` / `.risk-card` | 시스템 리스크와 기업별 리스크 |
| `.timeline` | AI 인프라 투자 사이클 |
| `.source-list` | 클릭 가능한 출처 링크 모음 |

## 4. Responsive Behavior

- 기본 컨테이너 폭은 `1120px`, 좌우 패딩은 데스크톱 `32px`, 모바일 `16px`.
- `760px` 이하에서 2단 레이아웃은 1단으로 전환한다.
- 모바일 통계 카드는 2열을 유지해 리포트 첫 화면의 정보 밀도를 보존한다.
- 표는 `overflow-x: auto`로 가로 스크롤을 허용한다.

## 5. Editorial Tone

투자 조언처럼 보이지 않게 “매수”, “저평가 확정”, “수익 보장” 표현은 사용하지 않는다. 대신 “관찰 포인트”, “조건부 매력도”, “상대 비교”, “리스크 대비 보상”이라는 표현을 사용한다.
