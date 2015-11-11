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



### AJAX ###

#### GET ####

From jQuery

```js
$.ajax({
  type: "GET",
  url: &lt;url>,
  data: &lt;data>
});
```

to Vanilla JS

```js
var get = new XMLHttpRequest();
get.open("GET", &lt;url>, true);
get.setRequestHeader("Content-Type", "application/x-www-form-urlencoded; charset=UTF-8");
get.send(&lt;data>);
```

#### JSON ####

From jQuery

```js
function getJSON(url, next) {
    $.getJSON(url, function (data) {
      next(null, data);
    }).error(function () {
      next(new Error("There was a connection error of some sort."));
    });
}

getJSON(&lt;url>, function (err, data) {
    if (err) {
      return err;
    }

    data;
});
```

to Vanilla JS

```js
function getJSON(url, next) {
    var request = new XMLHttpRequest();
    request.open("GET", url, true);
    request.send();

    request.addEventListener("load", function () {
        if (request.status < 200 && request.status >= 400) {
            return next(new Error("We reached our target server, but it returned an error."));
        }

        next(null, JSON.parse(request.responseText));
    });

    request.addEventListener("error", function () {
        return next(new Error("There was a connection error of some sort."));
    });
}

getJSON(&lt;url>, function (err, data) {
    if (err) {
      return err;
    }

    data;
});
```

#### POST ####

From jQuery

```js
$.ajax({
  type: "POST",
  url: &lt;url>,
  data: &lt;data>
});
```

to Vanilla JS

```js
var post = new XMLHttpRequest();
post.open("POST", &lt;url>, true);
post.setRequestHeader("Content-Type", "application/x-www-form-urlencoded; charset=UTF-8");
post.send(&lt;data>);
```

#### Request / Response ####

From jQuery

```js
function request(url, next) {
    $.ajax({
        type: 'GET',
        url: url,
        success: function(response) {
          next(null, response);
        },
        error: function() {
          next(new Error("There was a connection error of some sort."));
        }
    });
}

request(&gt;url>, function (err, response) {
    if (err) {
      return err;
    }

    response;
});
```

to Vanilla JS

```js
function request(url, next) {
    var request = new XMLHttpRequest();
    request.open("GET", url, true);
    request.send();

    request.addEventListener("load", function () {
        if (request.status < 200 && request.status >= 400) {
            return next(new Error("We reached our target server, but it returned an error."));
        }

        next(null, request.responseText);
    });

    request.addEventListener("error", function () {
        return next(new Error("There was a connection error of some sort."));
    });
}

request(&gt;url>, function (err, response) {
    if (err) {
      return err;
    }

    response;
});
```



### ÉFFETS ###

#### Animation ####

From jQuery

```js
function fadeIn($element, speed, next) {
    $element.css("opacity", "0").animate({ opacity: 1 }, speed, next);
}
fadeIn($(&lt;element>), 2000, function () {
  $(this).css("opacity", "");
});
```

to Vanilla JS

```js
function fadeIn(element, speed, next) {
    var last = +new Date(),
        tick = function () {
            element.style.opacity = +element.style.opacity + (new Date() - last) / speed;

            last = +new Date();

            if (+element.style.opacity < 1) {
                requestAnimationFrame(tick);
            } else if (next) {
                next.call(element);
            }
        };

    element.style.opacity = 0;
    tick();
}

fadeIn(&lt;element>, 2000, function () {
    this.style.opacity = '';
});
```

#### Hide ####

From jQuery

```js
$(&lt;element>).hide();
```

to Vanilla JS

```js
&lt;element>.style.display = "none";
```

#### Show ####

From jQuery

```js
$(&lt;element>).show();
```

to Vanilla JS

```js
&lt;element>.style.display = "";
```

### ÉLÉMENTS ###

#### Add Class ####

From jQuery

```js
$(&lt;element>).addClass(&lt;className>);
```

to Vanilla JS

```js
&lt;element>.classList.add(&lt;className>);
```

#### Append ####

From jQuery

```js
$(&lt;element>).append(&lt;movedElement>);
```

to Vanilla JS

```js
&lt;element>.appendChild(&lt;movedElement>);
// &lt;element>.insertAdjacentHTML("beforeEnd", "&lt;htmlString>");
```

#### Children ####

From jQuery

```js
$(&lt;element>).children();
```

to Vanilla JS

```js
&lt;element>.children;
```

#### Clone ####

From jQuery

```js
$(&lt;element>).clone();
```

to Vanilla JS

```js
&lt;element>.cloneNode(true);
```

#### Compare ####

From jQuery

```js
var $a = $(&lt;element>).find(&lt;otherElement>);
    $b = $(&lt;otherElement>);

$a.is($b);
```

to Vanilla JS

```js
var temp = document.getElementsByTagName(&lt;element>)[0],
    a = temp.getElementsByTagName(&lt;otherElement>)[0],
    b = document.querySelector(&lt;otherElement>);

(a === b);
```

#### Contains ####

From jQuery

```js
$.contains(&lt;element>, &lt;childrenElements>);
```

to Vanilla JS

```js
(&lt;element> !== &lt;childrenElements>) && &lt;element>.contains(&lt;childrenElements>);
```

#### Empty ####

From jQuery

```js
$(&lt;element>).empty();
```

to Vanilla JS

```js
&lt;element>.innerHTML = "";
```

#### Filter ####

From jQuery

```js
$(&lt;element>).filter(function (i, element) {
    return &lt;filterCondition>;
}).each(function (i, element) {
    element;
});
```

to Vanilla JS

```js
var elements = document.querySelectorAll(&lt;element>);

elements = [].filter.call(elements, function (element) {
    return &lt;filterCondition>;
});

[].forEach.call(elements, function (element) {
    element;
});
```

#### Find Children ####

From jQuery

```js
$(&lt;element>).find(&lt;childrenElements>);
```

to Vanilla JS

```js
&lt;element>.querySelectorAll(&lt;childrenElements>);
```

#### Get Attributes ####

From jQuery

```js
$(&lt;element>).attr(&lt;attributeName>);
```

to Vanilla JS

```js
&lt;element>.getAttribute(&lt;attributeName>);
```

#### Get HTML ####

From jQuery

```js
$(&lt;element>).html();
```

to Vanilla JS

```js
&lt;element>.innerHTML;
```

#### Get Node HTML ####

From jQuery

```js
$("&lt;div>").append($(&lt;element>).clone()).html();
```

to Vanilla JS

```js
&lt;element>.outerHTML;
```

#### Get Style ####

From jQuery

```js
$(&lt;element>).css(&lt;property>);
```

to Vanilla JS

```js
getComputedStyle(&lt;element>)[&lt;property>];
```

#### Get Text ####

From jQuery

```js
$(&lt;element>).text();
```

to Vanilla JS

```js
&lt;element>.textContent;
```

#### Has Class ####

From jQuery

```js
$(&lt;element>).hasClass(&lt;className>);
```

to Vanilla JS

```js
&lt;element>.classList.contains(&lt;className>);
```

#### Insert After ####

From jQuery

```js
$(&lt;element>).after(&lt;htmlString>);
```

to Vanilla JS

```js
&lt;element>.insertAdjacentHTML("afterend", &lt;htmlString>);
```

#### Insert Before ####

From jQuery

```js
$(&lt;element>).before(&lt;htmlString>);
```

to Vanilla JS

```js
&lt;element>.insertAdjacentHTML("beforebegin", &lt;htmlString>);
```

#### Matches Selector ####

From jQuery

```js
$(&lt;element>).is(&lt;selector>);
```

to Vanilla JS

```js
&lt;element>.matches(&lt;selector>);
```

#### Next ####

From jQuery

```js
$(&lt;element>).next();
```

to Vanilla JS

```js
&lt;element>.nextElementSibling;
```

#### Offset from Document ####

From jQuery

```js
$(&lt;element>).offset();
```

to Vanilla JS

```js
var rect = &lt;element>.getBoundingClientRect()
{
    top: rect.top + document.body.scrollTop,
    left: rect.left + document.body.scrollLeft
}
```

#### Offset from Parent ####

From jQuery

```js
$(&lt;element>).position();
```

to Vanilla JS

```js
{
    left: &lt;element>.offsetLeft,
    top: &lt;element>.offsetTop
}
```

#### Offset from Viewport ####

From jQuery

```js
$(&lt;element>).offset();
```

to Vanilla JS

```js
var rect = &lt;element>.getBoundingClientRect()
{
    top: rect.top + document.body.scrollTop,
    left: rect.left + document.body.scrollLeft
}
```

#### Outer Height ####

From jQuery

```js
$(&lt;element>).outerHeight();
```

to Vanilla JS

```js
&lt;element>.offsetHeight
```

#### Outer Width ####

From jQuery

```js
$(&lt;element>).outerWidth();
```

to Vanilla JS

```js
&lt;element>.offsetWidth
```

#### Parent ####

From jQuery

```js
$(&lt;element>).parent();
```

to Vanilla JS

```js
&lt;element>.parentNode;
```

#### Parent Not Static ####

From jQuery

```js
$(&lt;element>).offsetParent();
```

to Vanilla JS

```js
(&lt;element>.offsetParent || &lt;element>)
```

#### Prepend ####

From jQuery

```js
$(&lt;element>).prepend(&lt;movedElement>);
```

to Vanilla JS

```js
&lt;element>.insertBefore(&lt;movedElement>, &lt;element>.firstChild);
// &lt;element>.insertAdjacentHTML("afterBegin", "&lt;htmlString>");
```

#### Prev ####

From jQuery

```js
$(&lt;element>).prev();
```

to Vanilla JS

```js
&lt;element>.previousElementSibling;
```

#### Remove Class ####

From jQuery

```js
$(&lt;element>).remove();
```

to Vanilla JS

```js
&lt;element>.parentNode.removeChild(&lt;element>);
```

#### Remove Class ####

From jQuery

```js
$(&lt;element>).removeClass(&lt;className>);
```

to Vanilla JS

```js
&lt;element>.classList.remove(&lt;className>);
```

#### Set Attributes ####

From jQuery

```js
$(&lt;element>).attr(&lt;attributeName>, &lt;value>);
```

to Vanilla JS

```js
&lt;element>.setAttribute(&lt;attributeName>, &lt;value>);
```

#### Set HTML ####

From jQuery

```js
$(&lt;element>).html(&lt;htmlString>);
```

to Vanilla JS

```js
&lt;element>.innerHTML = &lt;htmlString>;
```

#### Set Node HTML ####

From jQuery

```js
$(&lt;element>).replaceWith(&lt;htmlString>);
```

to Vanilla JS

```js
&lt;element>.outerHTML = &lt;htmlString>;
```

#### Set Style ####

From jQuery

```js
$(&lt;element>).css(&lt;property>, &lt;value>);
```

to Vanilla JS

```js
&lt;element>.style.&lt;property> = &lt;value>;
```

#### Set Text ####

From jQuery

```js
$(&lt;element>).text(&lt;string>);
```

to Vanilla JS

```js
&lt;element>.textContent = &lt;string>;
```

#### Siblings ####

From jQuery

```js
$(&lt;element>).siblings();
```

to Vanilla JS

```js
[].filter.call(&lt;element>.parentNode.children, function (element) {
    return element !== &lt;element>;
});
```

#### Toggle Class ####

From jQuery

```js
$(&lt;element>).toggleClass(&lt;className>);
```

to Vanilla JS

```js
&lt;element>.classList.toggle(&lt;className>);
```

### ÉVÈNEMENTS ###

#### Load ####

From jQuery

```js
$(window).load(function () {
    // I am full loaded.
});
```

to Vanilla JS

```js
window.addEventListener("load", function () {
    // I am full loaded.
});
```

#### Off ####

From jQuery

```js
$(&lt;element>).off(&lt;eventName>, &lt;eventHandler>);
```

to Vanilla JS

```js
&lt;element>.removeEventListener(&lt;eventName>, &lt;eventHandler>);
```

#### On ####

From jQuery

```js
$(&lt;element>).on(&lt;eventName>, &lt;eventHandler>);
```

to Vanilla JS

```js
&lt;element>.addEventListener(&lt;eventName>, &lt;eventHandler>);
```

#### Ready ####

From jQuery

```js
$(document).ready(function () {
    // I am ready to be manipulate.
});
```

to Vanilla JS

```js
document.addEventListener("DOMContentLoaded", function () {
    // I am ready to be manipulate.
});
```

#### Trigger ####

From jQuery

```js
var event = jQuery.Event("click");
event.test = true;

$(&lt;element>).click(function (event) {
    event.test; // undefined by click, true by trigger.
});
$(&lt;element>).trigger(event);
// $(&lt;element>).trigger("click"); // Shortcut without test property.
```

to Vanilla JS

```js
var event = document.createEvent("HTMLEvents");
event.initEvent("click", true, false);
event.test = true;

&lt;element>.addEventListener("click", function (event) {
    event.test; // undefined by click, true by trigger.
});
&lt;element>.dispatchEvent(event);
```

### UTILES ###

#### Array Each ####

From jQuery

```js
$.each(&lt;array>, function (i, item) {
    (item === array[i]); // true
});
```

to Vanilla JS

```js
&lt;array>.forEach(function (item, i) {
    (item === array[i]); // true
});
```

#### Change Futur Context ####

From jQuery

```js
$.proxy(&lt;fn>, &lt;context>);
```

to Vanilla JS

```js
&lt;fn>.bind(&lt;context>);
```

#### Extend ####

From jQuery

```js
$.isArray(&lt;array>);
```

to Vanilla JS

```js
function extend(first) {
    var extended = first || {};

    for (var i = 1; i < arguments.length; i++) {
        if (!arguments[i]) {
            continue;
        }

        for (var key in arguments[i]) {
            if (arguments[i].hasOwnProperty(key)) {
                extended[key] = arguments[i][key];
            }
        }
    }

    return extended;
}

var object = extend(&lt;object1>, &lt;object2> ..., &lt;objectN>)
```

#### Index Of ####

From jQuery

```js
$.inArray(&lt;item>, &lt;array>);
```

to Vanilla JS

```js
[].indexOf(&lt;item>);
```

#### Is Array ####

From jQuery

```js
$.isArray(&lt;array>);
```

to Vanilla JS

```js
Array.isArray(&lt;array>);
```

#### Map ####

From jQuery

```js
$.map(&lt;array>, function (item, i) {
    return &lt;operations>;
});
```

to Vanilla JS

```js
&lt;array>.map(function (item, i) {
    return &lt;operations>;
});
```

#### Now ####

From jQuery

```js
$.now();
```

to Vanilla JS

```js
Date.now();
```

#### Parse HTML ####

From jQuery

```js
$.parseHTML(&lt;htmlString>);
```

to Vanilla JS

```js
function parseHTML(htmlString) {
    var body = document.implementation.createHTMLDocument().body;
    body.innerHTML = htmlString;
    return body.children;
}

parseHTML(&lt;htmlString>);
```

#### Parse JSON ####

From jQuery

```js
$.parseJSON(&lt;jsonString>);
```

to Vanilla JS

```js
JSON.parse(&lt;jsonString>);
```

#### Trim ####

From jQuery

```js
$.trim(&lt;string>);
```

to Vanilla JS

```js
&lt;string>.trim();
```
