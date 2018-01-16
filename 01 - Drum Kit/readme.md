# 01 - Javascript Drum Kit

Mini project using the keydown event and key detection to execute different sounds.

## Notes

Learning new concepts like [**`data-`**](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*) and tag [**`audio`**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio), [**`data-`**](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*) is for store some extra information in elements and [**`audio`**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) what is used to embed sound content in documents, also learned the [**`classList`**](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList) property to manipulate the DOM of an element.
```Javascript
/** Remove Transition function  **/
function removeTransition(e) {
  if (e.propertyName !== "transform") return;
  e.target.classList.remove("playing");
}

function playSound(e) {
  const audio = document.querySelector(`audio[data-key="${e.keyCode}"]`);
  const key = document.querySelector(`.key[data-key="${e.keyCode}"]`);
  if (!audio) return;

  key.classList.add("playing");
  audio.currentTime = 0;
  audio.play();
}

const keys = document.querySelectorAll(".key");
keys.forEach(key => key.addEventListener("transitionend", removeTransition));
window.addEventListener("keydown", playSound);
```

### [**Website**](http://js30-drum-kit.surge.sh) 
### [**Codepen**](https://codepen.io/cesaramirez/full/baxpQm)

### Links of Interest
### [KeyCode.info](http://keycode.info)