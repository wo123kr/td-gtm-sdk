# td-gtm-sdk

ThinkingEngine(TE) 운영 모듈 웹 JS SDK를 GTM(Google Tag Manager) 템플릿에서 `injectScript`로 로드하기 위한 **CDN 미러 레포지토리**.

공식 다운로드처는 [`download.thinkingdata.cn`](https://download.thinkingdata.cn/client/release/web_td_strategy.zip)이며, 본 레포는 GTM 템플릿에서 jsDelivr 경유로 불러오기 위한 재배포본입니다.

## 포함된 SDK

| 모듈 | 버전 | 파일 |
|---|---|---|
| TDAnalytics | 2.x | `web_analytics/thinkingdata.umd.min.js` |
| TDCore | 1.x | `web_core/tdcore.umd.min.js` |
| TDRemoteConfig | 1.2.1 | `web_remote_config/tdremoteconfig.umd.min.js` |
| TDStrategy | 1.x | `web_strategy/tdstrategy.umd.min.js` |

각 모듈은 UMD / ESM / CJS / AMD 4가지 번들 포맷을 제공합니다.

v1.3.0부터 [`web_td_strategy.zip`](https://download.thinkingdata.cn/client/release/web_td_strategy.zip) 기반 — 구성 센터(TDRemoteConfig) + 클라이언트 채널(TDStrategy) 전체 커버.

## 사용 (GTM injectScript 예시)

```html
<script src="https://cdn.jsdelivr.net/gh/wo123kr/td-gtm-sdk@v1.3.0/web_analytics/thinkingdata.umd.min.js"></script>
<script src="https://cdn.jsdelivr.net/gh/wo123kr/td-gtm-sdk@v1.3.0/web_core/tdcore.umd.min.js"></script>
<script src="https://cdn.jsdelivr.net/gh/wo123kr/td-gtm-sdk@v1.3.0/web_remote_config/tdremoteconfig.umd.min.js"></script>
<script src="https://cdn.jsdelivr.net/gh/wo123kr/td-gtm-sdk@v1.3.0/web_strategy/tdstrategy.umd.min.js"></script>
<script>
  TDApp.init({
    appId: "YOUR_APP_ID",
    serverUrl: "YOUR_SERVER_URL",
    enableLog: false,
    mode: "normal"
  });
</script>
```

## 버전

- `v1.3.0` (2026-04-20) — `web_td_strategy.zip` 기반, TDStrategy 번들 추가
- `v1.2.1` (2026-01-07) — `web_td_remote_config.zip` 기반 (TDRemoteConfig만)

## 업데이트 방법

1. [공식 SDK](https://download.thinkingdata.cn/client/release/web_td_strategy.zip) 다운로드 후 해제
2. `web_analytics/`, `web_core/`, `web_remote_config/`, `web_strategy/` 폴더 덮어쓰기
3. 버전 태그 생성 후 push:
   ```bash
   git tag vX.Y.Z
   git push --tags
   ```
4. jsDelivr URL 변경: `@vX.Y.Z/...`

## 라이선스

SDK 자체의 라이선스는 ThinkingData의 조건을 따릅니다. 본 레포는 단순 미러일 뿐 별도 라이선스를 부여하지 않습니다.
