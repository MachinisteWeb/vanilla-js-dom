# Vanilla JS #

**Vous êtes français ? Le README [derrière ce lien](http://blog.lesieur.name/vanilla-js-france/) vous sera peut-être plus agréable.**





## Overview ##

Vanilla JS is a fast, lightweight, cross-platform framework for building incredible, powerful JavaScript applications.

### Use in Development ###

Just put the following code:

```html
<script src="path/to/vanilla.js"></script>
```

### Use in Production ###

The much faster method:

```html

```





## Speed Comparison ##

### Retrieve DOM element by ID ###

|              | Code                                                                         | 100 ops Vanilla JS |
|--------------|------------------------------------------------------------------------------|-------------------:|
| Vanilla JS   | [document.getElementById("vanilla");](http://codepen.io/Haeresis/pen/RWeqaB) |                100 |
| Dojo         | [dojo.byId("dojo");](http://codepen.io/Haeresis/pen/yYQjxp)                  |                 92 |
| Prototype JS | [$("prototype");](http://codepen.io/Haeresis/pen/yYQjEP)                     |                 57 |
| jQuery       | [$("#jquery");](http://codepen.io/Haeresis/pen/EVOLLe)                       |                 42 |
| MooTools     | [document.id("mootools");](http://codepen.io/Haeresis/pen/gaQzQr)            |                 24 |

### Retrieve 10 DOM elements by tag name ###

|              | Code                                                                                  | 100 ops Vanilla JS |
|--------------|---------------------------------------------------------------------------------------|-------------------:|
| Vanilla JS   | [document.getElementsByTagName("div");](http://codepen.io/Haeresis/pen/BoGVzd)        |                100 |
| Prototype JS | [Prototype.Selector.select("div", document);](http://codepen.io/Haeresis/pen/LpXrOG)  |                 25 |
| jQuery       | [$("div");](http://codepen.io/Haeresis/pen/BoGVmJ)                                    |                 21 |
| jQuery       | [dojo.query("div");](http://codepen.io/Haeresis/pen/dYQKJX)                           |                  3 |
| MooTools     | [Slick.search(document, "div", new Elements);](http://codepen.io/Haeresis/pen/qOQKxO) |                  2 |
