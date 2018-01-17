# 02 - CSS + JS Clock

Challenge to make a clock with css and javascript using transforms

## Notes

The DOM of each hand of the clock was extracted and its [**`transform`**](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) style property was manipulated, previously the current time was obtained with the javascript method [**`Date`**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)

```Javascript
const secondHand = document.querySelector(".second-hand");
const minsHand = document.querySelector(".min-hand");
const hourHand = document.querySelector(".hour-hand");

var setDate = () => {
  const now = new Date();

  const seconds = now.getSeconds();
  const secondsDegrees = seconds / 60 * 360 + 90;
  secondHand.style.transform = `rotate(${secondsDegrees}deg)`;

  const mins = now.getMinutes();
  const minsDegrees = mins / 60 * 360 + seconds / 60 * 6 + 90;
  minsHand.style.transform = `rotate(${minsDegrees}deg)`;

  const hour = now.getHours();
  const hourDegrees = hour / 12 * 360 + mins / 60 * 30 + 90;
  hourHand.style.transform = `rotate(${hourDegrees}deg)`;
};

setInterval(setDate, 1000);

setDate();
```

### [**Website**](http://js30-js-css-clock.surge.sh) 
### [**Codepen**](https://codepen.io/cesaramirez/full/bamqEN)