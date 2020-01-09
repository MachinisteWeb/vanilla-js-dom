# Vanilla JS #

[![Faites un don](https://img.shields.io/badge/don-%E2%9D%A4-ddddff.svg)](https://www.paypal.me/BrunoLesieur/5) [![Build Passing](https://img.shields.io/badge/build-passing-brightgreen.svg)](https://github.com/Haeresis/vanilla-js-dom) [![Version 6.0](https://img.shields.io/badge/version-6.0-brightgreen.svg)](https://github.com/Haeresis/vanilla-js-dom) [![Technical Debt Ratio](https://img.shields.io/badge/debt_ratio-0%25-brightgreen.svg)](http://docs.sonarqube.org/display/PLUG/JavaScript+Plugin)

**Vous êtes français ? Le README [derrière ce lien](https://blog.lesieur.name/vanilla-js-france/) vous sera peut-être plus agréable.**

<img src="https://blog.lesieur.name/media/images/upload/vanilla.png" style="margin: 0 auto; display: block; max-width:100%;">





## Overview ##

Vanilla JS is a fast, lightweight, cross-platform tool for building incredible, powerful JavaScript applications.

### Use in Development ###

Just put the following code:

```html
<!-- <script src="path/to/vanilla.js"></script> -->
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
        - [[name]](#name)
        - [[tagname]](#tagname)
        - [Inverted Loop](#inverted-loop)
    - [AJAX](#ajax)
        - [GET](#get)
        - [JSON](#json)
        - [POST](#post)
        - [Request / Response](#request--response)
    - [ATTRIBUTES](#attributes)
        - [Add Class](#add-class)
        - [Get Attribute](#get-attribute)
        - [Get Data](#get-data)
        - [Get Value](#get-data)
        - [Has Class](#has-class)
        - [Remove Attribute](#remove-attribute)
        - [Remove Class](#remove-class)
        - [Remove Data](#remove-data)
        - [Set Attribute](#set-attribute)
        - [Set Data](#set-data)
        - [Set Value](#set-data)
        - [Toggle Class](#toggle-class)
    - [EFFECTS](#effects)
        - [Animation](#animation)
        - [Hide](#hide)
        - [Show](#show)
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
    - [MANIPULATION](#manipulation)
        - [Append](#append)
        - [Clone](#clone)
        - [Compare](#compare)
        - [Contains](#contains)
        - [Create](#create)
        - [Empty](#empty)
        - [Get HTML](#get-html)
        - [Get Node HTML](#get-node-html)
        - [Get Text](#get-text)
        - [Index From Parent](#index-from-parent)
        - [Insert After](#insert-after)
        - [Insert Before](#insert-before)
        - [Prepend](#prepend)
        - [Remove](#remove)
        - [Remove Children](#remove-children)
        - [Replace](#replace)
        - [Set HTML](#set-html)
        - [Set Node HTML](#set-node-html)
        - [Set Text](#set-text)
        - [Unwrap](#unwrap)
        - [Wrap](#wrap)
    - [TRAVERSING](#traversing)
        - [All Next](#all-next)
        - [All Parents](#all-parents)
        - [All Previous](#all-previous)
        - [Children](#children)
        - [Closest Parent](#closest-parent)
        - [Find Children](#find-children)
        - [First Child](#first-child)
        - [Last Child](#last-child)
        - [Matches Selector](#matches-selector)
        - [Next](#next)
        - [Next Until](#next-until)
        - [Parent](#parent)
        - [Parents](#parents)
        - [Previous](#previous)
        - [Previous Until](#previous-until)
        - [Siblings](#siblings)
    - [STYLES](#styles)
        - [Get Style](#get-style)
        - [Get Scroll Left](#get-scroll-left)
        - [Get Scroll Top](#get-scroll-top)
        - [Inner Height](#inner-height)
        - [Inner Width](#inner-width)
        - [Offset from Document](#offset-from-document)
        - [Offset from Parent](#offset-from-parent)
        - [Offset from Viewport](#offset-from-viewport)
        - [Outer Height](#outer-height)
        - [Outer Width](#outer-width)
        - [Parent Not Static](#parent-not-static)
        - [Set Style](#set-style)
        - [Set Scroll Left](#set-scroll-left)
        - [Set Scroll Top](#set-scroll-top)
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
        - [Parse XML](#parse-xml)
        - [Serialize Array](#serialize-array)
        - [Serialize String](#serialize-string)
        - [Trim](#trim)





## Speed Comparison ##

When Vanilla JS perform 100 operations, others do:

### Retrieve DOM element by ID ###

|              | Code                                                                         | 100 ops Vanilla JS |
|--------------|:-----------------------------------------------------------------------------|-------------------:|
| Vanilla JS   | [document.getElementById('vanilla');](http://codepen.io/Haeresis/pen/RWeqaB) |                100 |
| Dojo         | [dojo.byId('dojo');](http://codepen.io/Haeresis/pen/yYQjxp)                  |                 92 |
| Prototype JS | [$('prototype');](http://codepen.io/Haeresis/pen/yYQjEP)                     |                 57 |
| jQuery       | [$('#jquery');](http://codepen.io/Haeresis/pen/EVOLLe)                       |                 42 |
| MooTools     | [document.id('mootools');](http://codepen.io/Haeresis/pen/gaQzQr)            |                 24 |



### Retrieve 10 DOM elements by tag name ###

|              | Code                                                                                  | 100 ops Vanilla JS |
|--------------|:--------------------------------------------------------------------------------------|-------------------:|
| Vanilla JS   | [document.getElementsByTagName('div');](http://codepen.io/Haeresis/pen/BoGVzd)        |                100 |
| Prototype JS | [Prototype.Selector.select('div', document);](http://codepen.io/Haeresis/pen/LpXrOG)  |                 25 |
| jQuery       | [$('div');](http://codepen.io/Haeresis/pen/BoGVmJ)                                    |                 21 |
| Dojo         | [dojo.query('div');](http://codepen.io/Haeresis/pen/dYQKJX)                           |                  3 |
| MooTools     | [Slick.search(document, 'div', new Elements);](http://codepen.io/Haeresis/pen/qOQKxO) |                  2 |



### Vanilla JS vs jQuery ###

#### Retrieve 10 DOM elements by class name ####

|            | Code                                                                                 | 100 ops Vanilla JS |
|------------|:-------------------------------------------------------------------------------------|-------------------:|
| Vanilla JS | [document.getElementsByClassName('vanilla');](http://codepen.io/Haeresis/pen/ZbmRMN) |                100 |
| jQuery     | [$('.jquery');](http://codepen.io/Haeresis/pen/jbQKeQ)                               |                 25 |

#### Retrieve DOM element with `<#id> .inner span` selector ####

|            | Code                                                                                     | 100 ops Vanilla JS |
|------------|:-----------------------------------------------------------------------------------------|-------------------:|
| Vanilla JS | [document.querySelector('#vanilla .inner span');](http://codepen.io/Haeresis/pen/PPxaVQ) |                100 |
| jQuery     | [$('#jquery .inner span');](http://codepen.io/Haeresis/pen/YyRvgQ)                       |                 17 |

#### Retrieve 10 DOM elements with `<.className> .inner span` selector ####

|            | Code                                                                                        | 100 ops Vanilla JS |
|------------|:--------------------------------------------------------------------------------------------|-------------------:|
| Vanilla JS | [document.querySelectorAll('.vanilla .inner span');](http://codepen.io/Haeresis/pen/gaQKJv) |                100 |
| jQuery     | [$('.jquery .inner span');](http://codepen.io/Haeresis/pen/ojQyrZ)                          |                 51 |



### Vanilla JS Selector Performances ###

All tests are based on `<section id="vanilla" class="vanilla"><article class="inner"><div class="target" id="target"></div></article></section>` HTML.

| Select node `<div class="target" id="target"></div>`                                       | 100 ops Vanilla JS |
|:-------------------------------------------------------------------------------------------|-------------------:|
| [document.getElementsByTagName('div');](http://codepen.io/Haeresis/pen/PPxdWo)             |                100 |
| [document.getElementById('target');](http://codepen.io/Haeresis/pen/xwQaEz)                |                 99 |
| [document.getElementsByClassName('target');](http://codepen.io/Haeresis/pen/epQLBG)        |                 96 |
| [document.querySelector('.vanilla .inner div');](http://codepen.io/Haeresis/pen/qOQMRJ)    |                 68 |
| [document.querySelectorAll('.vanilla .inner div');](http://codepen.io/Haeresis/pen/epQLve) |                 35 |





## From jQuery to Vanilla JS ##

**Legend**

Understand each type of DOM Object:

```html
<div class="example">
  <span>(Text into) Html Element</span>
  <!-- Comment Element -->
  Text Element
  <span>(Text into) Html Element</span>
</div>
```

- `querySelector('.example')` return a `HTMLElement`.
- `querySelector('.example').children` return a `HTMLCollection`, each collection's item is a `HTMLElement`, two `[span, span]` here.
- `querySelector('.example').childNodes` return a `NodeList`, each collection's item is a `Node`, seven `[text, span, text, comment, text, span, text]` here.
- `querySelector('.example').childNodes[0]` return a `Text` (`Node`) of `typeNode` 3, as a text. (`...nodeList[3]` is `typeNode` 8 as a `Comment` (`Node` too)).

### .Node #Selector ###

#### #id ####

From jQuery

```js
var htmlElement = $('#id')[0];
```

to Vanilla JS

```js
var htmlElement = document.getElementById('id');
```

#### .classname #id tagname ####

From jQuery

```js
var htmlElement = $('#id .classname tagname')[0];
```

to Vanilla JS

```js
document.querySelector('#id .classname tagname');
```

#### [.classname #id tagname] ####

From jQuery

```js
$('#id .classname tagname').each(function (i, htmlElement) {
    htmlElement;
});
```

to Vanilla JS

```js
var nodeList = document.querySelectorAll('#id .classname tagname'); // Not Live (Snapshot)
[].forEach.call(nodeList, function (node) {
    node;
});
```

#### [.classname] ####

From jQuery

```js
$('.classname').each(function (i, htmlElement) {
    htmlElement;
});
```

to Vanilla JS

```js
var htmlCollection = document.getElementsByClassName('classname'); // Live
// var nodeList = document.querySelectorAll('.classname'); // Not Live (Snapshot)
[].forEach.call(htmlCollection, function (htmlElement) {
    htmlElement;
});
```

#### [name] ####

From jQuery

```js
$('[name="name"]').each(function (i, htmlElement) {
    htmlElement;
});
```

to Vanilla JS

```js
var nodeList = document.getElementsByName('name'); // Live
// var nodeList = document.querySelectorAll('[name=name]'); // Not Live (Snapshot)
[].forEach.call(nodeList, function (node) {
    node;
});
```

#### [tagname] ####

From jQuery

```js
$('tagname').each(function (i, htmlElement) {
    htmlElement;
});
```

to Vanilla JS

```js
var htmlCollection = document.getElementsByTagName('tagname'); // Live
// var nodeList = document.querySelectorAll('tagname'); // Not Live (Snapshot)
[].forEach.call(htmlCollection, function (htmlElement) {
    htmlElement;
});
```

#### Reverted Loop ####

From jQuery

```js
$($('.className').get().reverse()).each(function (i, htmlElement) {
    htmlElement;
});
```

to Vanilla JS

```js
var htmlCollection = document.getElementsByClassName('className'), // Live
    i = htmlCollection.length;
while (htmlElement = htmlCollection[--i]) {
    htmlElement;
}
```



### AJAX ###

#### GET ####

From jQuery

```js
$.ajax({
  type: 'GET',
  url: <url>,
  data: <data>
});
```

to Vanilla JS

```js
fetch(<url>, {
  method: 'GET',
  body: <data>
});

/* // IE fallback
var get = new XMLHttpRequest();
get.open('GET', <url>, true);
get.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded; charset=UTF-8');
get.send(<data>); */
```

#### JSON ####

From jQuery

```js
function getJSON(url, next) {
    $.getJSON(url, function (data) {
        next(null, data);
    }).error(function () {
        next(new Error('There was a connection error of some sort.'));
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
    fetch(url)
        .then(function (data) {
            if (data.status >= 200 && data.status < 300) {
                return data;
            }

            next(new Error('We reached our target server, but it returned an error.'));
        })
        .then(function (data) {
            next(null, data.json());
        })
        .catch(function () {
            next(new Error('There was a connection error of some sort.'));
        });
}

/* // IE fallback
function getJSON(url, next) {
    var request = new XMLHttpRequest();
    request.open('GET', url, true);
    request.send();

    request.addEventListener('load', function () {
        if (request.status < 200 && request.status >= 400) {
            return next(new Error('We reached our target server, but it returned an error.'));
        }

        next(null, JSON.parse(request.responseText));
    });

    request.addEventListener('error', function (error) {
        next(new Error('There was a connection error of some sort.'), error);
    });
} */

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
  type: 'POST',
  url: <url>,
  data: <data>
});
```

to Vanilla JS

```js
fetch(<url>, {
  method: 'POST',
  body: <data>
});

/* // IE fallback
var post = new XMLHttpRequest();
post.open('POST', <url>, true);
post.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded; charset=UTF-8');
post.send(<data>); */
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
          next(new Error('There was a connection error of some sort.'));
        }
    });
}

request(<url>, function (err, response) {
    if (err) {
      return err;
    }

    response;
});
```

to Vanilla JS

```js
function request(url, next) {
    fetch(url)
        .then(function (response) {
            if (response.status >= 200 && response.status < 300) {
                return response;
            }

            next(new Error('We reached our target server, but it returned an error.'));
        })
        .then(function (response) {
            next(null, response);
        })
        .catch(function () {
            next(new Error('There was a connection error of some sort.'));
        });
}

/* // IE fallback
function request(url, next) {
    var request = new XMLHttpRequest();
    request.open('GET', url, true);
    request.send();

    request.addEventListener('load', function () {
        if (request.status < 200 && request.status >= 400) {
            return next(new Error('We reached our target server, but it returned an error.'));
        }

        next(null, request.responseText);
    });

    request.addEventListener('error', function () {
        return next(new Error('There was a connection error of some sort.'));
    });
} */

request(<url>, function (err, response) {
    if (err) {
      return err;
    }

    response;
});
```



### ATTRIBUTES ###

#### Add Class ####

From jQuery

```js
$(<htmlElement>).addClass(<className>);
```

to Vanilla JS

```js
<htmlElement>.classList.add(<className>);
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
<htmlElement>.getAttribute('data-' + <dataName>);
```

#### Get Value ####

From jQuery

```js
$(<htmlElement>).val();
```

to Vanilla JS

```js
<htmlElement>.value;
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

#### Remove Attribute ####

From jQuery

```js
$(<htmlElement>).removeAttr(<attributeName>);
```

to Vanilla JS

```js
<htmlElement>.removeAttribute(<attributeName>);
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

#### Remove Data ####

From jQuery

```js
$(<htmlElement>).removeData(<dataName>);
```

to Vanilla JS

```js
<htmlElement>.removeAttribute('data-' + <dataName>);
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
<htmlElement>.setAttribute('data-' + <dataName>, <value>);
```

#### Set Value ####

From jQuery

```js
$(<htmlElement>).val(<value>);
```

to Vanilla JS

```js
<htmlElement>.value = <value>;
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



### EFFECTS ###

#### Animation ####

From jQuery

```js
function fadeIn($htmlElement, speed, next) {
    $htmlElement.css('opacity', '0').animate({ opacity: 1 }, speed, next);
}
fadeIn($(<htmlElement>), 2000, function () {
  $(this).css('opacity', '');
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
<htmlElement>.style.display = 'none';
```

#### Show ####

From jQuery

```js
$(<htmlElement>).show();
```

to Vanilla JS

```js
<htmlElement>.style.display = '';
```



### EVENTS ###

#### Hover ####

From jQuery

```js
$(<htmlElement>).hover(<eventHandlerMouseIn>, <eventHandlerMouseOut>);
```

to Vanilla JS

```js
<htmlElement>.addEventListener('mouseenter', <eventHandlerMouseIn>);
<htmlElement>.addEventListener('mouseleave', <eventHandlerMouseOut>);
```

#### Load ####

From jQuery

```js
$(<htmlElement>).load(function () {
    // I am full loaded.
});
```

to Vanilla JS

```js
<htmlElement>.addEventListener('load', function () {
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
<htmlElement>.addEventListener(<eventName>, <eventHandler>, { once: true });

/* // IE fallback
<htmlElement>.addEventListener(<eventName>, function callee(event) {
    event.target.removeEventListener(e.type, callee);
}); */
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
document.addEventListener('DOMContentLoaded', function () {
    // I am ready to be manipulate.
});
```

#### Trigger ####

From jQuery

```js
var event = jQuery.Event('click');
event.test = true;

$(<htmlElement>).click(function (event) {
    event.test; // undefined by click, true by trigger.
});
$(<htmlElement>).trigger(event);
// $(<htmlElement>).trigger('click'); // Shortcut without test property.
```

to Vanilla JS

```js
var event = new Event('click');
event.test = true;

<htmlElement>.addEventListener('click', function (event) {
    event.test; // undefined by click, true by trigger.
});
<htmlElement>.dispatchEvent(event);
```



### FILTERS ###

#### Filter ####

From jQuery

filterCondition

```js
$(<selector>).filter(function (i, htmlElement) {
    return <filterCondition>;
}).each(function (i, htmlElement) {
    htmlElement;
});
```

to Vanilla JS

```js
var nodeList = document.querySelectorAll(<selector>);

nodeList = [].filter.call(nodeList, function (node) {
    return <filterCondition>;
});

[].forEach.call(nodeList, function (node) {
    node;
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
// <htmlCollection>[0];
```

#### Has ####

From jQuery

```js
$(<selector>).has(<matchesChildSelector>);
```

to Vanilla JS

```js
var nodeList = document.querySelectorAll(<selector>);
[].filter.call(nodeList, function (node) {
    return node.querySelector(<matchesChildSelector>);
});
```

#### Is ####

From jQuery

```js
$(<selector>).is(<matchesSelector>);
```

to Vanilla JS

```js
var nodeList = document.querySelectorAll(<selector>);
[].some.call(nodeList, function (node) {
    return node.matches(<matchesSelector>);
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
// <htmlCollection>[<index>];
```

#### Last ####

From jQuery

```js
$(<selector>).last();
```

to Vanilla JS

```js
<htmlCollection>.item(<htmlCollection>.length - 1);
// <htmlCollection>[<htmlCollection>.length - 1];
```

#### Not ####

From jQuery

```js
$(<selector>).not(<matchesSelector>);
```

to Vanilla JS

```js
var nodeList = document.querySelectorAll(<selector>);
[].filter.call(nodeList, function (node) {
    return !node.matches(<matchesSelector>);
});
```

#### Slice ####

From jQuery

```js
$(<selector>).slice(<startIndex>, <endIndex>);
```

to Vanilla JS

```js
var nodeList = document.querySelectorAll(<selector>);
[].slice.call(nodeList, <startIndex>, <endIndex>);
```



### MANIPULATION ###

#### Append ####

From jQuery

```js
$(<htmlElement>).append($(<appendHtmlElement>));
// $(<htmlElement>).append(<appendHtmlElement>);
```

to Vanilla JS

```js
<htmlElement>.appendChild(<appendHtmlElement>);
// <htmlElement>.insertAdjacentHTML('beforeEnd', <htmlString>);
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
var $a = $(<selectorToFirstHtmlElement>).find(<selectorToSecondHtmlElement>);
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
$.contains($(<htmlElement>), $(<childHtmlElement>));
```

to Vanilla JS

```js
(<htmlElement> !== <childHtmlElement>) && <htmlElement>.contains(<childHtmlElement>);
```

#### Create ####

From jQuery

```js
$('<' + <tagString> + '>');
```

to Vanilla JS

```js
document.createElement(<tagString>);
```

#### Empty ####

From jQuery

```js
$(<htmlElement>).empty();
```

to Vanilla JS

```js
<htmlElement>.innerHTML = '';
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
$('<div>').append($(<htmlElement>).clone()).html();
```

to Vanilla JS

```js
<htmlElement>.outerHTML;
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

#### Index From Parent ####

From jQuery

```js
$(<htmlElement>).index();
```

to Vanilla JS

```js
[].slice.call(<htmlElement>.parentNode.children).indexOf(<htmlElement>);
```

#### Insert After ####

From jQuery

```js
$(<htmlElement>).after($(<afterHtmlElement>));
// $(<htmlElement>).after(<htmlString>);
```

to Vanilla JS

```js
<htmlElement>.parentNode.insertBefore(<afterHtmlElement>, <htmlElement>.nextSibling);
// <htmlElement>.insertAdjacentHTML('afterend', <htmlString>);
```

#### Insert Before ####

From jQuery

```js
$(<htmlElement>).before($(<beforeHtmlElement>));
// $(<htmlElement>).before(<htmlString>);
```

to Vanilla JS

```js
<htmlElement>.parentNode.insertBefore(<beforeHtmlElement>, <htmlElement>);
// <htmlElement>.insertAdjacentHTML('beforebegin', <htmlString>);
```

#### Prepend ####

From jQuery

```js
$(<htmlElement>).prepend($(<prependHtmlElement>));
// $(<htmlElement>).prepend(<htmlString>);
```

to Vanilla JS

```js
<htmlElement>.insertBefore(<prependHtmlElement>, <htmlElement>.firstChild);
// <htmlElement>.insertAdjacentHTML('afterBegin', <htmlString>);
```

#### Remove ####

From jQuery

```js
$(<htmlElement>).remove();
```

to Vanilla JS

```js
<htmlElement>.parentNode.removeChild(<htmlElement>);
```

#### Remove Children ####

From jQuery

```js
$(<htmlElement>).empty();
```

to Vanilla JS

```js
while (<htmlElement>.firstChild) {
    <htmlElement>.removeChild(<htmlElement>.firstChild);
}
// <htmlElement>.innerHTML = '';
```

#### Replace ####

From jQuery

```js
$(<htmlElement>).replaceWith($(<newHtmlElement>));
```

to Vanilla JS

```js
<htmlElement>.parentNode.replaceChild(<newHtmlElement>, <htmlElement>);
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

#### Set Text ####

From jQuery

```js
$(<htmlElement>).text(<string>);
```

to Vanilla JS

```js
<htmlElement>.textContent = <string>;
```

#### Unwrap ####

From jQuery

```js
$(<htmlElement>).unwrap();
```

to Vanilla JS

```js
while (<htmlElement>.firstChild) {
    <unwrapHtmlElement>.insertBefore(<htmlElement>.firstChild, <htmlElement>);
}
<unwrapHtmlElement>.removeChild(<htmlElement>);
```

#### Wrap ####

From jQuery

```js
$(<htmlElement>).wrap($(<wrapHtmlElement>));
```

to Vanilla JS

```js
<htmlElement>.parentNode.insertBefore(<wrapHtmlElement>, <htmlElement>);
<wrapHtmlElement>.appendChild(<htmlElement>);
```



### TRAVERSING ###

#### All Next ####

From jQuery

```js
$(<htmlElement>).nextAll();
```

to Vanilla JS

```js
var nextAll = false;
nextAll = [].filter.call(<htmlElement>.parentNode.children, function (htmlElement) {
    return (htmlElement.previousElementSibling === <htmlElement>) ? nextAll = true : nextAll;
});
```

#### All Parents ####

From jQuery

```js
var parents = $(<htmlElement>).parents();
```

to Vanilla JS

```js
var htmlElement = <htmlElement>,
    parents = [];
while (htmlElement = htmlElement.parentNode) {
    parents.push(htmlElement);
}
parents;
```

#### All Previous ####

From jQuery

```js
$(<htmlElement>).prevAll();
```

to Vanilla JS

```js
var prevAll = true;
prevAll = [].filter.call(<htmlElement>.parentNode.children, function (htmlElement) {
    return (htmlElement === <htmlElement>) ? prevAll = false : prevAll;
});
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

#### Closest Parent ####

From jQuery

```js
$(<htmlElement>).closest(<parentSelector>);
```

to Vanilla JS

```js
<htmlElement>.closest(<parentSelector>);

/* // IE fallback
var htmlElement = <htmlElement>,
    parents = [];
while (htmlElement = htmlElement.parentNode) {
    (htmlElement.matches && htmlElement.matches(<parentSelector>)) ? parents.push(htmlElement) : '';
}
parents[0]; */
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

#### First Child ####

From jQuery

```js
$(<htmlElement>).children().first();
```

to Vanilla JS

```js
<htmlElement>.firstChild();
```

#### Last Child ####

From jQuery

```js
$(<htmlElement>).children().last();
```

to Vanilla JS

```js
<htmlElement>.lastChild();
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
<htmlElement>.nextElementSibling; // HTMLElement
// <htmlElement>.nextSibling; // Node
```

#### Next Until ####

From jQuery

```js
$(<htmlElement>).nextUntil(<nextSelector>);
```

to Vanilla JS

```js
var htmlElement = <htmlElement>,
    nextUntil = [],
    until = true;
while (htmlElement = htmlElement.nextElementSibling) {
    (until && htmlElement && !htmlElement.matches(<nextSelector>)) ? nextUntil.push(htmlElement) : until = false;
}
nextUntil;
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

#### Parents ####

From jQuery

```js
var parents = $(<htmlElement>).parents(<parentSelector>);
```

to Vanilla JS

```js
var htmlElement = <htmlElement>,
    parents = [];
while (htmlElement = htmlElement.parentNode.closest(<parentSelector>)) {
    parents.push(htmlElement);
}
parents;

/* // IE fallback
var htmlElement = <htmlElement>,
    parents = [];
while (htmlElement = htmlElement.parentNode) {
    (htmlElement.matches && htmlElement.matches(<parentSelector>)) ? parents.push(htmlElement) : '';
}
parents; */
```

#### Parents Until ####

From jQuery

```js
var parents = $(<htmlElement>).parentsUntil(<parentSelector>);
```

to Vanilla JS

```js
var htmlElement = <htmlElement>,
    parentsUntil = [],
    until = true;
while (htmlElement = htmlElement.parentNode.closest(<parentSelector>)) {
    (until) ? parents.push(htmlElement) : until = false;
}
parentsUntil;

/* // IE fallback
var htmlElement = <htmlElement>,
    parentsUntil = [],
    until = true;
while (htmlElement = htmlElement.parentNode) {
    (until && htmlElement.matches && !htmlElement.matches(<parentSelector>)) ? parents.push(htmlElement) : until = false;
}
parentsUntil; */
```

#### Previous ####

From jQuery

```js
$(<htmlElement>).prev();
```

to Vanilla JS

```js
<htmlElement>.previousElementSibling; // HTMLElement
// <htmlElement>.previousSibling // Node;
```

#### Previous Until ####

From jQuery

```js
$(<htmlElement>).prevUntil(<previousSelector>);
```

to Vanilla JS

```js
var htmlElement = <htmlElement>,
    previousUntil = [],
    until = true;
while (htmlElement = htmlElement.previousElementSibling) {
    (until && htmlElement && !htmlElement.matches(<previousSelector>)) ? previousUntil.push(htmlElement) : until = false;
}
previousUntil;
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



### STYLES ###

#### Get Style ####

From jQuery

```js
$(<htmlElement>).css(<property>);
```

to Vanilla JS

```js
getComputedStyle(<htmlElement>)[<property>];
```

#### Get Scroll Left ####

From jQuery

```js
$(<htmlElement>).scrollLeft();
```

to Vanilla JS

```js
<htmlElement>.scrollLeft;
```

#### Get Scroll Top ####

From jQuery

```js
$(<htmlElement>).scrollTop();
```

to Vanilla JS

```js
<htmlElement>.scrollTop;
```

#### Inner Height ####

From jQuery

```js
$(<htmlElement>).innerHeight();
```

to Vanilla JS

```js
<htmlElement>.clientHeight
```

#### Inner Width ####

From jQuery

```js
$(<htmlElement>).innerWidth();
```

to Vanilla JS

```js
<htmlElement>.clientWidth
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

#### Parent Not Static ####

From jQuery

```js
$(<htmlElement>).offsetParent();
```

to Vanilla JS

```js
(<htmlElement>.offsetParent || <htmlElement>)
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

#### Set Scroll Left ####

From jQuery

```js
$(<htmlElement>).scrollLeft(<distance>);
```

to Vanilla JS

```js
<htmlElement>.scrollLeft = <distance>;
```

#### Set Scroll Top ####

From jQuery

```js
$(<htmlElement>).scrollTop(<distance>);
```

to Vanilla JS

```js
<htmlElement>.scrollTop = <distance>;
```



### UTILS ###

#### Array Each ####

From jQuery

```js
$.each(<array>, function (i, item) {
    (item === <array>[i]); // true
});
```

to Vanilla JS

```js
<array>.forEach(function (item, i) {
    (item === <array>[i]); // true
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
<object> = $.extend(<extendingObject>, <object>);
```

to Vanilla JS

```js
<object> = Object.assign(<object>, <extendingObject>);

/* // IE fallback (not deep)
Object.keys(<object>).forEach(function (key) {
    <object>[key] = (<extendingObject>[key]) ? <extendingObject>[key] : <object>[key];
});
<object>; */
```

#### Index Of ####

From jQuery

```js
$.inArray(<item>, <array>);
```

to Vanilla JS

```js
<array>.indexOf(<item>);
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
    return body.childNodes;
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

#### Parse XML ####

From jQuery

```js
$.parseXML(<xmlString>);
```

to Vanilla JS

```js
function parseXML(xmlString) {
    return (new DOMParser()).parseFromString(xmlString, 'text/xml');
}

parseXML(<xmlString>);
```

#### Serialize Array ####

From jQuery

```js
$.serializeArray(<form>);
```

to Vanilla JS

```js
function serializeArray(form) {
    var field, length, output = [];

    if (typeof form === 'object' && form.nodeName === 'FORM') {
        var length = form.elements.length;
        for (i = 0; i < length; i++) {
            field = form.elements[i];
            if (field.name && !field.disabled && field.type !== 'file' && field.type != 'reset' && field.type != 'submit' && field.type != 'button') {
                if (field.type === 'select-multiple') {
                    length = form.elements[i].options.length;
                    for (j = 0; j < length; j++) {
                        if(field.options[j].selected)
                            output[output.length] = { name: field.name, value: field.options[j].value };
                    }
                } else if ((field.type !== 'checkbox' && field.type !== 'radio') || field.checked) {
                    output[output.length] = { name: field.name, value: field.value };
                }
            }
        }
    }

    return output;
}
serializeArray(<form>);
```

#### Serialize String ####

From jQuery

```js
$.serialize(<form>);
```

to Vanilla JS

```js
function serialize(form) {
    var field, length, output = [];

    if (typeof form === 'object' && form.nodeName === 'FORM') {
        var length = form.elements.length;
        for (var i = 0; i < length; i++) {
            field = form.elements[i];
            if (field.name && !field.disabled && field.type !== 'file' && field.type !== 'reset' && field.type !== 'submit' && field.type !== 'button') {
                if (field.type === 'select-multiple') {
                    length = form.elements[i].options.length;
                    for (var j=0; j < length; j++) {
                        if (field.options[j].selected) {
                            output[output.length] = encodeURIComponent(field.name) + '=' + encodeURIComponent(field.options[j].value);
                        }
                    }
                } else if ((field.type !== 'checkbox' && field.type !== 'radio') || field.checked) {
                    output[output.length] = encodeURIComponent(field.name) + '=' + encodeURIComponent(field.value);
                }
            }
        }
    }

    return output.join('&').replace(/%20/g, '+');
}
serialize(<form>);
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
