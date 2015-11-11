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



### Vanilla JS vs jQuery ###

#### Retrieve 10 DOM elements by class name ####

|            | Code                                                                                 | 100 ops Vanilla JS |
|------------|--------------------------------------------------------------------------------------|-------------------:|
| Vanilla JS | [document.getElementsByClassName("vanilla");](http://codepen.io/Haeresis/pen/ZbmRMN) |                100 |
| jQuery     | [$(".jquery");](http://codepen.io/Haeresis/pen/jbQKeQ)                               |                 25 |

#### Retrieve DOM element with `<#id> .inner span` selector ####

|            | Code                                                                                     | 100 ops Vanilla JS |
|------------|------------------------------------------------------------------------------------------|-------------------:|
| Vanilla JS | [document.querySelector("#vanilla .inner span");](http://codepen.io/Haeresis/pen/PPxaVQ) |                100 |
| jQuery     | [$("#jquery .inner span");](http://codepen.io/Haeresis/pen/YyRvgQ)                       |                 17 |

#### Retrieve 10 DOM elements with `<.className> .inner span` selector ####

|            | Code                                                                                        | 100 ops Vanilla JS |
|------------|---------------------------------------------------------------------------------------------|-------------------:|
| Vanilla JS | [document.querySelectorAll(".vanilla .inner span");](http://codepen.io/Haeresis/pen/gaQKJv) |                100 |
| jQuery     | [$(".jquery .inner span");](http://codepen.io/Haeresis/pen/ojQyrZ)                          |                 51 |



### Vanilla JS Selector Performances ###

All tests are based on `<section id="vanilla" class="vanilla"><article class="inner"><div class="target" id="target"></div></article></section>` HTML.

| Selectionner le noeud `<div class="target" id="target"></div>`                             | 100 ops Vanilla JS |
|--------------------------------------------------------------------------------------------|-------------------:|
| [document.getElementsByTagName("div");](http://codepen.io/Haeresis/pen/PPxdWo)             |                100 |
| [document.getElementById("target");](http://codepen.io/Haeresis/pen/xwQaEz)                |                 99 |
| [document.getElementsByClassName("target");](http://codepen.io/Haeresis/pen/epQLBG)        |                 96 |
| [document.querySelector(".vanilla .inner div");](http://codepen.io/Haeresis/pen/qOQMRJ)    |                 68 |
| [document.querySelectorAll(".vanilla .inner div");](http://codepen.io/Haeresis/pen/epQLve) |                 35 |





## From jQuery to Vanilla JS ##

### .Selector #Dom ###

#### #id ####

From jQuery

```js
$("#id")[0];
```

to Vanilla JS

```js
document.getElementById("id");
```

#### .classname #id tagname ####

From jQuery

```js
$("#id .classname tagname")[0];
```

to Vanilla JS

```js
document.querySelector("#id .classname tagname");</code></pre>
    </blockquote>
</div>
```

#### [.classname #id tagname] ####

From jQuery

```js
$("#id .classname tagname").each(function (i, element) {
    element;
});
```

to Vanilla JS

```js
var elements = document.querySelectorAll("#id .classname tagname");
[].forEach.call(elements, function (element) {
    element;
});
```

#### [.classname] ####

From jQuery

```js
$(".classname").each(function (i, element) {
    element;
});
```

to Vanilla JS

```js
var elements = document.getElementsByClassName(".classname");
[].forEach.call(elements, function(element) {
    element;
});
```

#### [tagname] ####

From jQuery

```js
$("div").each(function (i, element) {
    element;
});
```

to Vanilla JS

```js
var elements = document.getElementsByTagName("div");
[].forEach.call(elements, function(element) {
    element;
});
```

