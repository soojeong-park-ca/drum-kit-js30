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
<video src="[embed my vid]" type="video/mp4" controls>

### Demo Link

- Live Site URL: (to be added soon)

## About the Project

### Status

🛠 Currently working on :

- deploying the app

### Built with

- HTML
- CSS
- Vanilla JS

### Reflection

This was a quick and easy project built as I started taking the JavaScript 30 course by Wes Bos. Project goals included using just Vanilla JS to build a website. I decided to build first before listening to lectures because that’s how I learn best.

One new thing I learned from this project is using the paused attribute and currentTime property. I used these to reset the audio whenever the audio was supposed to be replayed before it finished playing the whole sound.

```js
/* audio play function */
function playAudio(e) {
  // find the key element that matches the key pressed
  const pressedKey = document.querySelector(`.key-${e.keyCode}`);

  // find the audio element that matches the key pressed
  const audioToPlay = document.querySelector(`.audio-${e.keyCode}`);

  // if pressedKey exists:
  //--1. add "playing" class then remove
  pressedKey?.classList.add("playing");
  setTimeout(function () {
    pressedKey?.classList.remove("playing");
  }, 100);
  //--2. play the corresponding audio
  if (!audioToPlay) return;
  if (audioToPlay) {
    // ❗️ make audio play again from start if key is pressed again before audio ends
    // console.log(audioToPlay.paused);
    //-- when audio is done playing the whole sound
    if (audioToPlay.paused) audioToPlay.play();
    //-- when audio is not done playing the whole sound, reset the audio
    else audioToPlay.currentTime = 0;
  }
}
```

The technologies implemented in this project are HTML, CSS, and Vanilla JavaScript. It was a quick but super fun project and I got to work with audio elements for the first time!

## Author

Soojeong Park [@codingsooj](https://twitter.com/codingsooj)
