# earnings-cal

한국 주식시장 결산기별 실적 발표 구간과 정기보고서 법정 마감일을 담은 iCalendar 피드.

- 파일: `earnings_season.ics`
- 생성: 맥미니 `~/.bloomberg-monitor/earnings_season_ics.py` (launchd `com.ssenepodd.earnings-season-ics`, 매월 1일·16일)
- 원천: 정기보고서 법정 제출기한(분·반기 = 기간종료+45일, 사업보고서 = 사업연도말+90일)과 KRX 개장 캘린더. 전부 결정론적이라 몇 년 전부터 확정이다.

구독: 구글 캘린더 → 다른 캘린더 → URL로 추가 → 아래 주소

```
https://raw.githubusercontent.com/ssenepodd/earnings-cal/main/earnings_season.ics
```

이 저장소에는 공개 시장 일정만 들어간다. 시크릿·계좌·보유 정보는 넣지 않는다.
