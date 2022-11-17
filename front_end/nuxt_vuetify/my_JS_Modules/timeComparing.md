# TimeComparing.js
- JS로 비교 대상 시간과 현재시간의 차이를 비교한다.
- param
  - targetTime(String) : 현재 시각 비교 대상 시간
- return
  - elapsedMin(String) : 현재 시각과의 차이 분(minute) 값
```js
export const TimeComparing = (targetTime) => {
  const nowTemp = new Date();

  // 현재시간
  const nowYear = nowTemp.getFullYear(); // 연도
  const nowMonth = nowTemp.getMonth() + 1; // 월
  const nowDay = nowTemp.getDate(); // 일
  const nowHours = nowTemp.getHours(); // 현재 시간
  const nowMinutes = nowTemp.getMinutes(); // 현재 분

  // 비교시간
  // 예제에서 시간의 string 값이 yyyy-mm-ddThh:mm:ss 형태로 넘어오고
  // 위 형태를 파싱하는 부분이라서 파라미터 값에 맞게 수정이 필요함.
  const paresRegex = /T|:|-/g;
  targetTime = targetTime.replace(paresRegex, ".");
  targetTime = targetTime.split(".");

  const targetYear = targetTime[1]; // 연도
  const targetMonth = targetTime[2]; // 월
  const targetDay = targetTime[3]; // 일
  const targetHours = targetTime[4]; // 현재 시간
  const targetMinutes = targetTime[5]; // 현재 분
 
  const now = new Date(nowYear, nowMonth, nowDay, nowHours, nowMinutes); // 현재

  const target = new Date(
    targetYear,
    targetMonth,
    targetDay,
    targetHours,
    targetMinutes
  ); // 파라미터
  
  //현재 시간이 타겟 시간으로 부터 얼마나 경과했는지를 구한다.
  //다른 비교가 필요하다면 이 부분을 수정.
  const elapsedMSec = target.getTime() - now.getTime();
  return elapsedMSec / 1000 / 60;
};

```
