```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>倒计时</title>
</head>

<body>
  <div>距离2030年1月1日0时0分0秒还有：</div>
  <div id="leftNow"></div>
  <script src="../libs/jquery-3.2.1.min.js"></script>
  <script>
    $(function () {
      leftTimer(2030,1,1,0,0,0,"leftNow");
    })

    function leftTimer(year, month, day, hour, minute, second,timebox) {
      var leftTime = (new Date(year, month - 1, day, hour, minute, second)) - (new Date()); //计算剩余的毫秒数 
      var days = parseInt(leftTime / 1000 / 60 / 60 / 24, 10); //计算剩余的天数 
      var hours = parseInt(leftTime / 1000 / 60 / 60 % 24, 10); //计算剩余的小时 
      var minutes = parseInt(leftTime / 1000 / 60 % 60, 10); //计算剩余的分钟 
      var seconds = parseInt(leftTime / 1000 % 60, 10); //计算剩余的秒数 
      if ((days <= 0) && (hours <= 0) && (minutes <= 0) && (seconds <= 0)) {
        days = 0;
        hours = 0;
        minutes = 0;
        seconds = 0;
        window.clearInterval(timerNew)
      }
      days = checkTime(days);
      hours = checkTime(hours);
      minutes = checkTime(minutes);
      seconds = checkTime(seconds);
      var timerNew = setInterval("leftTimer(2030,1,1,0,0,0,'leftNow')", 1000);
      document.getElementById(timebox).innerHTML = days + "天" + hours + "时" + minutes + "分" +
        seconds+"秒";
    }
    function checkTime(i) { //将0-9的数字前面加上0，例1变为01 
      if (i < 10) {
        i = "0" + i;
      }
      return i;
    }
  </script>
</body>

</html>
```