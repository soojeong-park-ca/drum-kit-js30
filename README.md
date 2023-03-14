# JavaScript Drum Kit

Drum kit built with Vanilla JavaScript.

## Table of contents

- [Overview](#overview)
  - [Screenshots](#screenshots)
  - [Demo Link](#demo-link)
- [About the Project](#about-the-project)
  - [Status](#status)
  - [Built with](#built-with)
  - [Reflection](#reflection)
- [Author](#author)

## Overview

### Screenshots

Demo video:
<video src="https://user-images.githubusercontent.com/126619528/224394931-ace995c0-7e74-4462-84b3-45869ccfc3a0.mov" type="video/mp4" controls>

### Demo Link

**[💻 Live Site URL](https://soojeong-park-ca.github.io/drum-kit-js30/)**

## About the Project

### Status

✅ Completed & Deployed

### Built with

- HTML
- CSS
- Vanilla JS

### Reflection

This was a quick and easy project built as I started taking the JavaScript 30 course by Wes Bos. Project goals included using just Vanilla JS to build a website. I decided to build first before listening to lectures because that’s how I learn best.

Some features to highlight in this project are:

using the `currentTime` property to reset the audio whenever the audio is supposed to reset before it finishes playing the whole sound

```js
/* function */
function playAudio(e) {
  // find the key element that matches the key pressed
  const pressedKey = document.querySelector(`.key[data-key="${e.keyCode}"]`);

  // find the audio element that matches the key pressed
  const audioToPlay = document.querySelector(`audio[data-key="${e.keyCode}"]`);

  // if pressedKey exists:
  //--1. add "playing" class then remove
  pressedKey?.classList.add("playing");
  //--2. play the corresponding audio
  if (!audioToPlay) return;
  // ❗️ make audio play again from start if key is pressed again before audio ends
  //---a. reset audio
  else audioToPlay.currentTime = 0;
  //---b. play audio
  audioToPlay.play();
}
```

using `transitionend` event in an event listener to toggle a class instead of using setTimeout()

```js
// toggle 'playing' class
window.addEventListener("transitionend", e => {
  if (e.propertyName !== "transform") return;
  e.target.classList.remove("playing");
});
```

The technologies implemented in this project are HTML, CSS, and Vanilla JavaScript. It was a quick but super fun project and I got to work with audio elements for the first time!

## Author

Soojeong Park [@codingsooj](https://twitter.com/codingsooj)
