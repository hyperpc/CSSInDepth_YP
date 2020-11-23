
![Cover](img/CSSInDepth_Cover.jpg)  
ebook online: https://livebook.manning.com/book/css-in-depth/about-this-book/

## ch01 basic

advice on selector:

1. not use #ID selector;
2. not use !important;

inherit, initial, auto, inline,

Top->Right->Bottom->Left,
box-shadow

## ch02 Related Unit

1in = 25.4mm = 2.54cm = 6pc = 72pt = 96px,
em, rem

> Advice: rem for font-size; px for border; em for others.

@media

viewBox,
--main-bg, var(--main-bg),
document.documentElement,
getComputedStyle(elements),
styles.getPropertyValue('--main-bg'),
elements.style.setProperty('--main-bg', 'blue')

## ch03 box

> IE bug: render main as inline. To fix, using display: block.

aside, box-sizing, content-box, border-box,
float, overflow, display: table, display:table-cell,border-spacing: 1.5em,0;
Flexbox, display: flex, min-height, max-height, min-width, max-width
> Don't set height on an element, before you cannot find a solution.  
> Don't set overflow on an element, before you cannot find a solution.  
> margin-left, margin-top less then 0, diff with margin-right, margin-bottom less then 0

margin (top/bottom) folder,
.button-link+.button-link, body *+*,

## ch04 float

float, display:inline-block, display:table,
double container pattern, BFC(block formatting context),
> add whitespace before/after "-" in calc().

[class*='column-'], clearfix, ::before, ::after,
container, row, column, gutter, outline

## ch05 Flexbox

flex container, flex item,
display: flex/inline-flex/inline-block;
flex (flex-grow, flex-shrink, flex-basis),

flex-content: 
flex-direction: column/row/column-reverse/row-reverse;
input:not[type=radio],
flex-wrap:nowrap/wrap/wrap-reverse;
flex-flow(flex-direction/flex-wrap);
justify-content: flex-start/ flex-end/ center/ space-between/ space-around;
align-items: flex-start/ flex-end/ center/ stretch/ baseline;
align-content: flex-start/ flex-end/ center/ space-between/ space-around;

flex-item:
flex (flex-grow, flex-shrink, flex-basis),
align-self: auto/ flex-start/ flex-end/ center/ stretch/ baseline;
Order: 0; (default)

> autoprefixer for old browsers.  
> align-items/align-self: center will make content vertical center.  
> Flexbox make column same height.

## ch06 Grid

grid container, grid items, grid line, grid track, grid cell, grid area,
fr: fraction unit,
display: grid; grid-template-columns: 2fr 1fr; grid-template-rows: repeat(4, auto);
grid-template-columns: [left-start] 2fr [left-end right-start] 1fr [right-end];
grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
gap: 1.5em; grid-column: 1/3; grid-row: span 1;grid-column: left-start/right-end;
grid-template-areas, grid-area,
@supports(display: grid){}, justify-content/-items/-self, align-content/-items/-self,

## ch07 Position

fixed, relative, absolute,
content:"\00D7",
position: sticky;

## ch08 Responsive

1. mobile first
2. media query : @media, and, ","
3. fluid layout/ liquid layout
4. responsive image: srcset
5. viewport: meta

text-shadow, text-transform: uppercase;
media feature, media type(print/screen), min-width, max-width, orientation: landscape/portrait,
min-resolution, max-resolution, -webkit-min-device-pixel-ratio,
container query, element query,
img: srcset

## ch09 modular css

> normalize.css
Block, Modifier(message--error, nav-menu--horizontal), Element(media__title, media__item),
state class: is-open, is-expanded, is-loading, has-error.
utility.css
main.scss: @import 'button';

1. OOCSS : Object Orient CSS
2. SMACSS : Scalable and Modular Architecture for CSS
3. BEM : Block, Element, Modifier
4. ITCSS : Invert Triangle CSS

## ch10 pattern library

CSS first.

style guide generator, KSS(Knyle Style Sheets).

> cd /proj/pattern-lib  
> npm init -y pattern-lib  
> npm install --save-dev kss

package.json, kss-config.json,

```json
    "scripts":{
        "build":"kss --config kss-config.json"
    }
```

> npm run build

```css
    /*
        Media

        Display an image...

        Markup:
        <div class="media">
            <img class="media__image" src="...">
        </div>

        Styleguide Media
     */
```

> npm run build  
> section-media.html

SemVer : Semantic Version

## ch11 background, shadow and mixed module

line-gradient(), to right, 90deg, 5rad, 0.25turn, 400grad,
repeating-linear-gradient(), radial-gradient(), repeating-radial-gradient(),
color stop,
box-shadow, text-shadow,
background-blend-mode: multiply/ darken/ color-burn;
background-blend-mode: screen/ lighten/ color-dodge;
background-blend-mode: overlay/ hard-light/ soft-light;
background-blend-mode: Hue/ saturation/ luminosity/ color;
background-blend-mode: difference/ exclusion;
mix-blend-mode: hard-light/...

## ch12 Contrast, Color and Space

variable: --gray:#868e96;  
BEM : hero__inner;  
RGB/ RGBA/ HSL/ HSLA;  
> HSL COLOR PICKER: https://hslpicker.com/  
> Contrast Ratio: https://contrast-ratio.com/  
> CONTRAST CHECKER: https://contrastchecker.com/  
WCAG: AA/ AAA,  
leading (line-height)

## ch13 Web Font

Web safe font: Arial, Helvetica, Georgia;
@font-face;
Blog: Forum, Open Sans;
Children: Anton, Pangolin;

Typekit
Webtype
google fonts (Sansita, Roboto)

FOUT/ FOIN
line-height, letter-spacing,
font-display

## ch14 Transition

transition-property, transition-duration, transition-timing-function, transition-delay,  
linear/ ease/ ease in/ ease out,  
bezier curve, cubic-bezier, steps() end is default,  
handles, control points

## ch15 Transform

transform: rotate, translate, scale, skew  
point of origin; transform-origin: right center; transform-origin: 100% 50%;  
:nth-child(),  
rending: layout/reflow -> paint/layers(hardware acceleration) -> composite  
Recommend to use **transform**, **opacity** to do animation, not recommend **scale** or **transition**! Cause **transform**, **opacity** can take advantage of GPU hardware acceleration.  
**will-change:transform;** will advance make browser know that element transform will change. but this may take lots of system resource, not recommend.  
perspective, perspective-origin, backface-visibility:hidden; **transform-style:preserve-3d;(IE not support preserve-3d)**  
