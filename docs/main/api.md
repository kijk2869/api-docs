# API

이곳에서는 API 요청의 기본적인 정보를 안내합니다.

## Base URL

모든 API의 기본 URL입니다.

###### Base URL: https://api.koreanbots.dev

모든 엔드포인트의 요청은 이곳으로 보내게됩니다.

## 레이트리밋

<div class="ui error message"> 레이트리밋(RateLimit)은 로그인 토큰 기준이 아닌, IP 기준으로 적용됩니다. <br/> 레이트리밋은 클라이언트와 동일 IP로 접속할 경우 공유하게 됩니다.</div>

효율적인 리소스 관리를 위해 일정시간의 요청 제한 시간입니다.

만약 제한된 요청 횟수보다 더 많이 요청할 경우 `429`의 **STATUSCODE**(상태코드)를 반환합니다.

### 엔드포인트별 레이트리밋

반환 상태코드가 `200`(SUCCESS)가 아니어도 레이트리밋은 카운트됩니다.

| ENDPOINT | RATELIMIT |
| -------- | --------- |
| /*       | 120회/분  |
| /bots/servers | 1회/분 |

#### 레이트리밋 헤더

| 헤더명 | 설명 |
|-------|------|
| x-ratelimit-limit | 해당 엔드포인트에서 허용되는 요청 횟수입니다. |
| x-ratelimit-remaining | 남은 요청 가능 횟수입니다. |
| x-ratelimit-reset | 횟수 카운트가 리셋되는 시간입니다. |
