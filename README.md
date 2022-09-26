# Founders-and-Coders-Feature-project

## Etch-a-sketch feature for Founders and Coders application

### Planning

Coming from a theatrical background I've always loved interaction with an audience/user and sensory effects that affect the audience/user and add to their experience. Once I'd got a little HTML and CSS under my belt it wasn't long before I started to play around with different graphics, animations and effects.

The Etch-a-sketch feature was an early step of mine to begin to investigate the Canvas API. I have been studying the beginner javascript course by Wes Bos and one of the videos introduces students to Canvas. The concept seemed interesting to me since it would allow me to create interactive graphics on the screen, something i enjoy very much since it's engaging and creative for the user experience.

I looked into vanilla javascript 3-d animations such as this one `https://www.youtube.com/watch?v=ZWXgyTldjps` by _Navid Dev_ although I felt the explanation wasn't clear enough for me at this point and there was a real chance of me getting into the pattern of just copying what Navid was doing without learning what the steps were doing.

This `https://codepen.io/franksLaboratory/pens/popular` by _Franks Laboratory_ also caught my eye but again I felt that to grasp the basics of the Canvas API I should start with the Wes Bos canvas tutorial since I had access to Wes's course github repo and his instruction is very clear and detailed. Canvas seemed like a good place to begin my graphics journey since from the _MDN web docs_ I could see browser compatibility was green across the board ✅

### Building

When building the etch-a-sketch initially I made sure I paused to understand exactly how each of the steps were being implemented and what their purpose was as well as taking time to go and investigate the Canvas API docs at _MDN web docs_ `https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API`. Throughout this application process I've relied heavily on good docs and the _MDN Canvas API_ docs did not disappoint.

Although I used a tutorial to expose me to the basic concepts of canvas and give me a clear view of how many of the canvas methods intersect with each other I made sure I refactored the code in order to grasp a good understanding and realise my own goals. This is a starting point in an open ended project after all and a jump off point into further learning rather than an open and close case.

#### Refactoring

I made some changes to the code so as to explore canvas and see what I could do with it.

By declaring `@type {HTMLCanvasElement}` at the top of my feature.js I was able to gain access to the auto complete feature for properties and methods of HTMLCanvasElement.

`ctx.lineJoin = 'bevel';`
`ctx.lineCap = 'square';`
`ctx.lineWidth = MOVE_AMOUNT;`

`let hue = 0;`
`let shadowHue = 0;`
`ctx.strokeStyle =` `hsl(${hue}, 100%, 50%);`
`ctx.shadowColor =` `hsl(${shadowHue}, 100%, 50%);`
`ctx.shadowBlur = 15;`

Playing around with the Canvas property values above and adding in some great looking `ctx.shadowBlur` with a `ctx.shadowColor` of `hsl(0, 100%, 50%)` which increments by `shadowHue + shadowHue + 10` every `keydown` and also upping the `ctx.shadowBlur` to a value of `75`.

Inside of the _Clear/shake_ function I wanted to make sure the drawing started again at a random point and that the first stroke was visible to the user after the canvas had been cleared.

`ctx.beginPath(); // start the drawing again at a random point in state`
`x = Math.floor(Math.random() * width);`
`y = Math.floor(Math.random() * height);`
`ctx.moveTo(x, y);`
`ctx.lineTo(x, y);`
`ctx.stroke();`

Add `eventListener('touchstart')` to left touch button. next job is to add to all buttons and add logic which enables movement of stroke on touch devices.

### Debugging

Due to the way that I built this feature by learning it piece by piece I've only just started to hit debugging issues. Below are some of the issues I'm working on currently.

### Issues

- add touch control for mobile such as button icons with
  `addEventListener('touchstart')`
  `addEventListener('touchmove')`
  `addEventListener('touchend')`

- add switch statement for touch direction buttons
