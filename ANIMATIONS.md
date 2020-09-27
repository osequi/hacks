# Animations

- None of them is perfect
- The learning curve is high
- You can run in problems anytime with any of the libraries

## GSAP 

- 11k stars
- Can't do CSS animations: https://www.smashingmagazine.com/2020/09/animating-react-components-greensock/

## Anime.js

- 36k stars
- Very nice and easy
- Cannot combine initial transforms (`rotateY: 90deg`) of an element with a later keyframes animation addition (`translateX from -100 to 100`). The result is `transform: rotateY(90deg) translatex(-100 to 100)` versus `transform: rotateY(90deg); animation: <something which does translateX(-100 to 100)` See https://github.com/osequi/react-css-perspective/commit/d146fda49a418aa34878d3db3b935ccdeb4c946e

## Framer Motion

- 7k stars
- Very complex features like gesture control and so on
- Syntax is React-like
- It seemed more complicated than Anime.js

## React Spring 

- 18k stars
- The syntax is so complicated. I couldn't create a simple keyframes transitions like at https://css-tricks.com/how-css-perspective-works/?utm_source=CSS-Weekly&utm_campaign=Issue-427&utm_medium=email
