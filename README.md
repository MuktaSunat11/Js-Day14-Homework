# Digital-Clock
This is a simple digital clock that displays the current time in hours, minutes, seconds, and AM/PM.

# Html file
```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Digital Clock</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <h2>Digital Clock</h2>
    <div class="clock">
      <div>
        <span id="hour">00</span>
        <span class="text">Hours</span>
      </div>
      <div>
        <span id="minutes">00</span>
        <span class="text">Minutes</span>
      </div>
      <div>
        <span id="seconds">00</span>
        <span class="text">Seconds</span>
      </div>
      <div>
        <span id="ampm">AM</span>
      </div>
    </div>
    <script src="script.js"></script>
  </body>
</html>
```

# Css file
```
body {
    margin: 0;
    font-family: sans-serif;
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100vh;
    justify-content: center;
    background-size: cover;
    background-image: url("Clock\ bg.jpg");
    overflow: hidden;
  }
  
  h2 {
    text-transform: uppercase;
    letter-spacing: 4px;
    font-size: 14px;
    text-align: center;
    color: white;
  }
  
  .clock {
    display: flex;
  }
  
  .clock div {
    margin: 5px;
    position: relative;
  }
  
  .clock span {
    width: 100px;
    height: 80px;
    background: slateblue;
    opacity: 0.8;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 50px;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
  }
  
  .clock .text {
    height: 30px;
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 2px;
    background: darkblue;
    opacity: 0.8;
  }
  
  .clock #ampm {
    bottom: 0;
    position: absolute;
    width: 60px;
    height: 30px;
    font-size: 20px;
    background: green;
  }
```

# Javascript file
```
const hour = document.getElementById("hour");
const minute = document.getElementById("minutes");
const second = document.getElementById("seconds");
const ampm = document.getElementById("ampm");

function updateClock() {
  let h = new Date().getHours();
  let m = new Date().getMinutes();
  let s = new Date().getSeconds();
  let ampm = "AM";

  if (h > 12) {
    h = h - 12;
    ampm = "PM";
  }

  h = h < 10 ? "0" + h : h;
  m = m < 10 ? "0" + m : m;
  s = s < 10 ? "0" + s : s;

  hour.innerText = h;
  minute.innerText = m;
  second.innerText = s;
  ampm.innerText = ampm;
  setTimeout(() => {
    updateClock();
  }, 1000);
}

updateClock();
```
