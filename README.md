# earnings-cal

주식 투자 일정 iCalendar 피드 두 개. 맥미니 launchd 잡이 굽고 여기로 푸시하며, 구글 캘린더가 raw URL 을 구독한다.

## 1. 시장 캘린더 `earnings_season.ics`

- 생성: 맥미니 `~/.bloomberg-monitor/market_feed_ics.py` + `market_feed.py` (launchd `com.ssenepodd.market-feed-ics`, 매월 1일·16일 08:20)
- 레인 다섯: 한국 실적 시즌·정기보고서 마감(법정 기한 + KRX 캘린더, 결정론) · 한국 구조(선물옵션 만기·개장·폐장·배당락·코스피200 정기변경, 규칙 계산) · FOMC(연준 공식 캘린더) · 미국 주요 지표(FRED Release API) · 해외 대형주 실적(yfinance, 대부분 추정이라 제목에 (예상))
- 파일명은 첫 버전(실적 시즌 전용) 때 정한 것이고 구독 URL 이라 그대로 둔다. 캘린더에 보이는 이름은 「시장 캘린더」.

```
https://raw.githubusercontent.com/ssenepodd/earnings-cal/main/earnings_season.ics
```

## 2. 주간 프리뷰 · 영향도 랭킹 `weekly_preview.ics`

- 생성: 맥미니 `~/.bloomberg-monitor/weekly_preview_calendar.py` (주간 프리뷰가 저장되면 곧바로 + launchd `com.ssenepodd.weekly-preview-calendar` 월 06:30·09:00 백스톱)
- 내용: 매주 월요일 새벽 주간 프리뷰 P1 「영향도 랭킹 · 한국장 세션 기준」에 오른 이벤트를 한국장 영향일에 종일 이벤트로 놓는다. 제목 앞 `[N위]` 가 그 주 랭킹, 괄호는 KST 발표 시각. 날짜가 확정되지 않은 항목은 월~금 구간에 걸치고 `(날짜 미확정)` 을 단다. 최근 12주치를 담는다.
- 문서에서 추출한 항목마다 원문 인용을 대조해 원문에 없는 것은 넣지 않는다. 그래도 이 피드는 문서 해석 결과라 1번 피드(결정론)보다 신뢰 등급이 낮다.

```
https://raw.githubusercontent.com/ssenepodd/earnings-cal/main/weekly_preview.ics
```

## 구독

구글 캘린더 → 다른 캘린더 → URL로 추가 → 위 주소. 구글의 외부 ICS 폴링은 몇 시간에서 하루가 걸린다.

⛔리포 이름과 두 파일명은 구독 URL 이라 바꾸지 않는다. 바꾸면 404 인데 구글은 옛 사본을 계속 보여줘서 눈치채기 어렵다.

이 저장소에는 공개 시장 일정만 들어간다. 시크릿·계좌·보유 정보는 넣지 않는다.
