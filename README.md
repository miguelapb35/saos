# Svelte Animation on Scroll

A very small svelte component to animate your elements on scroll

SAoS allows you to animate once or multiple times a element on scroll, you can define the top and bottom "triggers" and the css of the internal divs (not recomended, but can help in some cases), see below the demo, how install and some examples :smile_cat:

### :zap: [Demo](https://shiryel.github.io/saos/)

---

## How to install

- Npm
```
npm i saos --save
```

- Yarn
```
yarn add saos
```

## How to use

Basic usage:
- First import the package on Svelte
```js
import Saos from "saos";
```

- Then define your @keyframes animation as a -global- on svelte
```css
@keyframes -global-from-left {
  0% {
    transform: rotateX(50deg) translateX(-200vw) skewX(-50deg);
    opacity: 1;
  }
  100% {
    transform: rotateX(0deg) translateX(0) skewX(0deg);
    opacity: 1;
  }
}
```

- Finally add the keyframe name without the -global- and the others animations params
```html
<Saos animation={"from-left 4s cubic-bezier(0.35, 0.5, 0.65, 0.95) both"}>
  <div><p>animation: from-left</p></div>
</Saos>
```

Beyond the animation param, you can use:
- animation_out -> to play a animation when the element is no more "visible" (use the top and bottom to define this), default: "none; opacity: 0"
- once -> if the animation will be played only one time or multiple times, default: false
- top -> the top of the observer, use a positive value to play the animation after top be visible, default: 0
- bottom -> the bottom of the observer, use a positive value to play the animation after bottom be visible, default: 0
- css_observer -> the css of the div that is the observer, not recomended to use, but is here :cat2:, default: ""
- css_animation -> the css of the div that is the animation, not recomended to use, but is here :cat2:, default: ""

### [You can see a bunch of usage here](https://github.com/shiryel/saos/blob/master/demo/src/Animations.svelte)

If you are lazy (like me) to create your own animations, take a look at [animista](https://animista.net/play/)
