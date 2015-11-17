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





## Summary ##

- [Overview](#overview)
    - [Use in Development](#use-in-development)
    - [Use in Production](#use-in-production)
- [Summary](#summary)
- [Speed Comparison](#speed-comparison)
    - [Retrieve DOM element by ID](#retrieve-dom-element-by-id)
    - [Retrieve 10 DOM elements by tag name](#retrieve-10-dom-elements-by-tag-name)
    - [Vanilla JS vs jQuery](#vanilla-js-vs-jquery)
        - [Retrieve 10 DOM elements by class name](#retrieve-10-dom-elements-by-class-name)
        - [Retrieve DOM element with <#id> .inner span selector](#retrieve-dom-element-with-id-inner-span-selector)
        - [Retrieve 10 DOM elements with <.className> .inner span selector](#retrieve-10-dom-elements-with-classname-inner-span-selector)
    - [Vanilla JS Selector Performances](#vanilla-js-selector-performances)
- [From jQuery to Vanilla JS](#from-jquery-to-vanilla-js)
    - [.Selector #Dom](#selector-dom)
        - [#id](#id)
        - [.classname #id tagname](#classname-id-tagname)
        - [[.classname #id tagname]](#classname-id-tagname-1)
        - [[.classname]](#classname)
        - [[tagname]](#tagname)
    - [AJAX](#ajax)
        - [GET](#get)
        - [JSON](#json)
        - [POST](#post)
        - [Request / Response](#request--response)
    - [EFFECTS](#effects)
        - [Animation](#animation)
        - [Hide](#hide)
        - [Show](#show)
    - [ELEMENTS](#elements)
        - [Add Class](#add-class)
        - [Append](#append)
        - [Children](#children)
        - [Clone](#clone)
        - [Compare](#compare)
        - [Contains](#contains)
        - [Empty](#empty)
        - [Find Children](#find-children)
        - [Get Attribute](#get-attribute)
        - [Get Data](#get-data)
        - [Get HTML](#get-html)
        - [Get Node HTML](#get-node-html)
        - [Get Style](#get-style)
        - [Get Text](#get-text)
        - [Has Class](#has-class)
        - [Insert After](#insert-after)
        - [Insert Before](#insert-before)
        - [Matches Selector](#matches-selector)
        - [Next](#next)
        - [Offset from Document](#offset-from-document)
        - [Offset from Parent](#offset-from-parent)
        - [Offset from Viewport](#offset-from-viewport)
        - [Outer Height](#outer-height)
        - [Outer Width](#outer-width)
        - [Parent](#parent)
        - [Parent Not Static](#parent-not-static)
        - [Prepend](#prepend)
        - [Prev](#prev)
        - [Remove Class](#remove-class)
        - [Remove Class](#remove-class)
        - [Set Attribute](#set-attribute)
        - [Set Data](#set-data)
        - [Set HTML](#set-html)
        - [Set Node HTML](#set-node-html)
        - [Set Style](#set-style)
        - [Set Text](#set-text)
        - [Siblings](#siblings)
        - [Toggle Class](#toggle-class)
    - [EVENTS](#events)
        - [Hover](#hover)
        - [Load](#load)
        - [Off](#off)
        - [On](#on)
        - [One](#one)
        - [Ready](#ready)
        - [Trigger](#trigger)
    - [FILTERS](#filters)
        - [Filter](#filter)
        - [First](#first)
        - [Item](#item)
        - [Has](#has)
        - [Is](#is)
        - [Last](#last)
        - [Not](#not)
        - [Slice](#slice)
    - [UTILS](#utils)
        - [Array Each](#array-each)
        - [Change Futur Context](#change-futur-context)
        - [Extend](#extend)
        - [Index Of](#index-of)
        - [Is Array](#is-array)
        - [Map](#map)
        - [Now](#now)
        - [Parse HTML](#parse-html)
        - [Parse JSON](#parse-json)
        - [Trim](#trim)





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
var htmlElement = $("#id")[0];
```

to Vanilla JS

```js
var htmlElement = document.getElementById("id");
```

#### .classname #id tagname ####

From jQuery

```js
var htmlElement = $("#id .classname tagname")[0];
```

to Vanilla JS

```js
document.querySelector("#id .classname tagname");
```

#### [.classname #id tagname] ####

From jQuery

```js
$("#id .classname tagname").each(function (i, htmlElement) {
    htmlElement;
});
```

to Vanilla JS

```js
var htmlCollection = document.querySelectorAll("#id .classname tagname");
[].forEach.call(htmlCollection, function (htmlElement) {
    htmlElement;
});
```

#### [.classname] ####

From jQuery

```js
$(".classname").each(function (i, htmlElement) {
    htmlElement;
});
```

to Vanilla JS

```js
var htmlCollection = document.getElementsByClassName(".classname");
[].forEach.call(htmlCollection, function (htmlElement) {
    htmlElement;
});
```

#### [tagname] ####

From jQuery

```js
$("tagname").each(function (i, htmlElement) {
    htmlElement;
});
```

to Vanilla JS

```js
var htmlCollection = document.getElementsByTagName("tagname");
[].forEach.call(htmlCollection, function (htmlElement) {
    htmlElement;
});
```



### AJAX ###

#### GET ####

From jQuery

```js
$.ajax({
  type: "GET",
  url: <url>,
  data: <data>
});
```

to Vanilla JS

```js
var get = new XMLHttpRequest();
get.open("GET", <url>, true);
get.setRequestHeader("Content-Type", "application/x-www-form-urlencoded; charset=UTF-8");
get.send(<data>);
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

getJSON(<url>, function (err, data) {
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

getJSON(<url>, function (err, data) {
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
  url: <url>,
  data: <data>
});
```

to Vanilla JS

```js
var post = new XMLHttpRequest();
post.open("POST", <url>, true);
post.setRequestHeader("Content-Type", "application/x-www-form-urlencoded; charset=UTF-8");
post.send(<data>);
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



### EFFECTS ###

#### Animation ####

From jQuery

```js
function fadeIn($htmlElement, speed, next) {
    $htmlElement.css("opacity", "0").animate({ opacity: 1 }, speed, next);
}
fadeIn($(<htmlElement>), 2000, function () {
  $(this).css("opacity", "");
});
```

to Vanilla JS

```js
function fadeIn(htmlElement, speed, next) {
    var last = +new Date(),
        tick = function () {
            htmlElement.style.opacity = +htmlElement.style.opacity + (new Date() - last) / speed;

            last = +new Date();

            if (+htmlElement.style.opacity < 1) {
                requestAnimationFrame(tick);
            } else if (next) {
                next.call(htmlElement);
            }
        };

    htmlElement.style.opacity = 0;
    tick();
}

fadeIn(<htmlElement>, 2000, function () {
    this.style.opacity = '';
});
```

#### Hide ####

From jQuery

```js
$(<htmlElement>).hide();
```

to Vanilla JS

```js
<htmlElement>.style.display = "none";
```

#### Show ####

From jQuery

```js
$(<htmlElement>).show();
```

to Vanilla JS

```js
<htmlElement>.style.display = "";
```



### ELEMENTS ###

#### Add Class ####

From jQuery

```js
$(<htmlElement>).addClass(<className>);
```

to Vanilla JS

```js
<htmlElement>.classList.add(<className>);
```

#### Append ####

From jQuery

```js
$(<htmlElement>).append(<movedElement>);
```

to Vanilla JS

```js
<htmlElement>.appendChild(<movedElement>);
// <htmlElement>.insertAdjacentHTML("beforeEnd", "<htmlString>");
```

#### Children ####

From jQuery

```js
$(<htmlElement>).children();
```

to Vanilla JS

```js
<htmlElement>.children;
```

#### Clone ####

From jQuery

```js
$(<htmlElement>).clone();
```

to Vanilla JS

```js
<htmlElement>.cloneNode(true);
```

#### Compare ####

From jQuery

```js
var $a = $(<firstHtmlElement>).find(<selectorToSecondHtmlElement>);
    $b = $(<selectorToSecondHtmlElement>);

$a.is($b);
```

to Vanilla JS

```js
var temp = document.getElementsByTagName(<selectorToFirstHtmlElement>)[0],
    a = temp.getElementsByTagName(<selectorToSecondHtmlElement>)[0],
    b = document.querySelector(<selectorToSecondHtmlElement>);

(a === b);
```

#### Contains ####

From jQuery

```js
$.contains(<htmlElement>, <childHtmlElement>);
```

to Vanilla JS

```js
(<htmlElement> !== <childHtmlElement>) && <htmlElement>.contains(<childHtmlElement>);
```

#### Empty ####

From jQuery

```js
$(<htmlElement>).empty();
```

to Vanilla JS

```js
<htmlElement>.innerHTML = "";
```

#### Find Children ####

From jQuery

```js
$(<htmlElement>).find(<childrenSelector>);
```

to Vanilla JS

```js
<htmlElement>.querySelectorAll(<childrenSelector>);
```

#### Get Attribute ####

From jQuery

```js
$(<htmlElement>).attr(<attributeName>);
```

to Vanilla JS

```js
<htmlElement>.getAttribute(<attributeName>);
```

#### Get Data ####

From jQuery

```js
$(<htmlElement>).data(<dataName>);
```

to Vanilla JS

```js
<htmlElement>.getAttribute(<"data-" + dataName>);
```

#### Get HTML ####

From jQuery

```js
$(<htmlElement>).html();
```

to Vanilla JS

```js
<htmlElement>.innerHTML;
```

#### Get Node HTML ####

From jQuery

```js
$("<div>").append($(<htmlElement>).clone()).html();
```

to Vanilla JS

```js
<htmlElement>.outerHTML;
```

#### Get Style ####

From jQuery

```js
$(<htmlElement>).css(<property>);
```

to Vanilla JS

```js
getComputedStyle(<htmlElement>)[<property>];
```

#### Get Text ####

From jQuery

```js
$(<htmlElement>).text();
```

to Vanilla JS

```js
<htmlElement>.textContent;
```

#### Has Class ####

From jQuery

```js
$(<htmlElement>).hasClass(<className>);
```

to Vanilla JS

```js
<htmlElement>.classList.contains(<className>);
```

#### Insert After ####

From jQuery

```js
$(<htmlElement>).after(<htmlString>);
```

to Vanilla JS

```js
<htmlElement>.insertAdjacentHTML("afterend", <htmlString>);
```

#### Insert Before ####

From jQuery

```js
$(<htmlElement>).before(<htmlString>);
```

to Vanilla JS

```js
<htmlElement>.insertAdjacentHTML("beforebegin", <htmlString>);
```

#### Matches Selector ####

From jQuery

```js
$(<htmlElement>).is(<selector>);
```

to Vanilla JS

```js
<htmlElement>.matches(<selector>);
```

#### Next ####

From jQuery

```js
$(<htmlElement>).next();
```

to Vanilla JS

```js
<htmlElement>.nextElementSibling;
```

#### Offset from Document ####

From jQuery

```js
$(<htmlElement>).offset();
```

to Vanilla JS

```js
var rect = <htmlElement>.getBoundingClientRect()
{
    top: rect.top + document.body.scrollTop,
    left: rect.left + document.body.scrollLeft
}
```

#### Offset from Parent ####

From jQuery

```js
$(<htmlElement>).position();
```

to Vanilla JS

```js
{
    left: <htmlElement>.offsetLeft,
    top: <htmlElement>.offsetTop
}
```

#### Offset from Viewport ####

From jQuery

```js
$(<htmlElement>).offset();
```

to Vanilla JS

```js
var rect = <htmlElement>.getBoundingClientRect()
{
    top: rect.top + document.body.scrollTop,
    left: rect.left + document.body.scrollLeft
}
```

#### Outer Height ####

From jQuery

```js
$(<htmlElement>).outerHeight();
```

to Vanilla JS

```js
<htmlElement>.offsetHeight
```

#### Outer Width ####

From jQuery

```js
$(<htmlElement>).outerWidth();
```

to Vanilla JS

```js
<htmlElement>.offsetWidth
```

#### Parent ####

From jQuery

```js
$(<htmlElement>).parent();
```

to Vanilla JS

```js
<htmlElement>.parentNode;
```

#### Parent Not Static ####

From jQuery

```js
$(<htmlElement>).offsetParent();
```

to Vanilla JS

```js
(<htmlElement>.offsetParent || <htmlElement>)
```

#### Prepend ####

From jQuery

```js
$(<htmlElement>).prepend(<movedElement>);
```

to Vanilla JS

```js
<htmlElement>.insertBefore(<movedElement>, <htmlElement>.firstChild);
// <htmlElement>.insertAdjacentHTML("afterBegin", "<htmlString>");
```

#### Prev ####

From jQuery

```js
$(<htmlElement>).prev();
```

to Vanilla JS

```js
<htmlElement>.previousElementSibling;
```

#### Remove Class ####

From jQuery

```js
$(<htmlElement>).remove();
```

to Vanilla JS

```js
<htmlElement>.parentNode.removeChild(<htmlElement>);
```

#### Remove Class ####

From jQuery

```js
$(<htmlElement>).removeClass(<className>);
```

to Vanilla JS

```js
<htmlElement>.classList.remove(<className>);
```

#### Set Attribute ####

From jQuery

```js
$(<htmlElement>).attr(<attributeName>, <value>);
```

to Vanilla JS

```js
<htmlElement>.setAttribute(<attributeName>, <value>);
```

#### Set Data ####

From jQuery

```js
$(<htmlElement>).data(<dataName>, <value>);
```

to Vanilla JS

```js
<htmlElement>.setAttribute(<"data-" + dataName>, <value>);
```

#### Set HTML ####

From jQuery

```js
$(<htmlElement>).html(<htmlString>);
```

to Vanilla JS

```js
<htmlElement>.innerHTML = <htmlString>;
```

#### Set Node HTML ####

From jQuery

```js
$(<htmlElement>).replaceWith(<htmlString>);
```

to Vanilla JS

```js
<htmlElement>.outerHTML = <htmlString>;
```

#### Set Style ####

From jQuery

```js
$(<htmlElement>).css(<property>, <value>);
```

to Vanilla JS

```js
<htmlElement>.style.<property> = <value>;
```

#### Set Text ####

From jQuery

```js
$(<htmlElement>).text(<string>);
```

to Vanilla JS

```js
<htmlElement>.textContent = <string>;
```

#### Siblings ####

From jQuery

```js
$(<htmlElement>).siblings();
```

to Vanilla JS

```js
[].filter.call(<htmlElement>.parentNode.children, function (htmlElement) {
    return htmlElement !== <htmlElement>;
});
```

#### Toggle Class ####

From jQuery

```js
$(<htmlElement>).toggleClass(<className>);
```

to Vanilla JS

```js
<htmlElement>.classList.toggle(<className>);
```



### EVENTS ###

#### Hover ####

From jQuery

```js
$(<htmlElement>).hover(<eventHandlerMouseIn>, <eventHandlerMouseOut>);
```

to Vanilla JS

```js
<htmlElement>.addEventListener("mouseenter", <eventHandlerMouseIn>);
<htmlElement>.addEventListener("mouseleave", <eventHandlerMouseOut>);
```

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
$(<htmlElement>).off(<eventName>, <eventHandler>);
```

to Vanilla JS

```js
<htmlElement>.removeEventListener(<eventName>, <eventHandler>);
```

#### On ####

From jQuery

```js
$(<htmlElement>).on(<eventName>, <eventHandler>);
```

to Vanilla JS

```js
<htmlElement>.addEventListener(<eventName>, <eventHandler>);
```

#### One ####

From jQuery

```js
$(<htmlElement>).one(<eventName>, <eventHandler>);
```

to Vanilla JS

```js
<htmlElement>.addEventListener(<eventName>, function callee(event) {
    event.target.removeEventListener(e.type, callee);
});
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

$(<htmlElement>).click(function (event) {
    event.test; // undefined by click, true by trigger.
});
$(<htmlElement>).trigger(event);
// $(<htmlElement>).trigger("click"); // Shortcut without test property.
```

to Vanilla JS

```js
var event = document.createEvent("HTMLEvents");
event.initEvent("click", true, false);
event.test = true;

<htmlElement>.addEventListener("click", function (event) {
    event.test; // undefined by click, true by trigger.
});
<htmlElement>.dispatchEvent(event);
```



### FILTERS ###

#### Filter ####

From jQuery

```js
$(<selector>).filter(function (i, htmlElement) {
    return <filterCondition>;
}).each(function (i, htmlElement) {
    htmlElement;
});
```

to Vanilla JS

```js
var htmlCollection = document.querySelectorAll(<selector>);

htmlCollection = [].filter.call(htmlCollection, function (htmlElement) {
    return <filterCondition>;
});

[].forEach.call(htmlCollection, function (htmlElement) {
    htmlElement;
});
```

#### First ####

From jQuery

```js
$(<selector>).first();
```

to Vanilla JS

```js
<htmlCollection>.item(0);
// <htmlCollection>[0]
```

#### Has ####

From jQuery

```js
$(<selector>).has(<matchesChildSelector>);
```

to Vanilla JS

```js
var htmlCollection = document.querySelectorAll(<selector>);
[].filter.call(htmlCollection, function (htmlElement) {
    return htmlElement.querySelector(<matchesChildSelector>);
});
```

#### Is ####

From jQuery

```js
$(<selector>).is(<matchesSelector>);
```

to Vanilla JS

```js
var htmlCollection = document.querySelectorAll(<selector>);
[].some.call(htmlCollection, function (htmlElement) {
    return htmlElement.matches(<matchesSelector>);
});
```

#### Item ####

From jQuery

```js
$(<selector>).eq(<index>);
```

to Vanilla JS

```js
<htmlCollection>.item(<index>);
// <htmlCollection>[<index>]
```

#### Last ####

From jQuery

```js
$(<selector>).last();
```

to Vanilla JS

```js
<htmlCollection>.item(<htmlCollection>.length - 1);
// <htmlCollection>[<htmlCollection>.length - 1]
```

#### Not ####

From jQuery

```js
$(<selector>).not(<matchesSelector>);
```

to Vanilla JS

```js
var htmlCollection = document.querySelectorAll(<selector>);
[].forEach.call(htmlCollection, function (htmlElement) {
    return !htmlElement.matches(<matchesSelector>);
});
```

#### Slice ####

From jQuery

```js
$(&lt;selector>).slice(<startIndex>, <endIndex>);
```

to Vanilla JS

```js
var htmlCollection = document.querySelectorAll(&lt;selector>);
[].slice.call(htmlCollection, <startIndex>, <endIndex>);
```



### UTILS ###

#### Array Each ####

From jQuery

```js
$.each(<array>, function (i, item) {
    (item === array[i]); // true
});
```

to Vanilla JS

```js
<array>.forEach(function (item, i) {
    (item === array[i]); // true
});
```

#### Change Futur Context ####

From jQuery

```js
$.proxy(<fn>, <context>);
```

to Vanilla JS

```js
<fn>.bind(<context>);
```

#### Extend ####

From jQuery

```js
$.isArray(<array>);
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

var object = extend(<object1>, <object2> ..., <objectN>)
```

#### Index Of ####

From jQuery

```js
$.inArray(<item>, <array>);
```

to Vanilla JS

```js
[].indexOf(<item>);
```

#### Is Array ####

From jQuery

```js
$.isArray(<array>);
```

to Vanilla JS

```js
Array.isArray(<array>);
```

#### Map ####

From jQuery

```js
$.map(<array>, function (item, i) {
    return <operations>;
});
```

to Vanilla JS

```js
<array>.map(function (item, i) {
    return <operations>;
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
$.parseHTML(<htmlString>);
```

to Vanilla JS

```js
function parseHTML(htmlString) {
    var body = document.implementation.createHTMLDocument().body;
    body.innerHTML = htmlString;
    return body.children;
}

parseHTML(<htmlString>);
```

#### Parse JSON ####

From jQuery

```js
$.parseJSON(<jsonString>);
```

to Vanilla JS

```js
JSON.parse(<jsonString>);
```

#### Trim ####

From jQuery

```js
$.trim(<string>);
```

to Vanilla JS

```js
<string>.trim();
```
