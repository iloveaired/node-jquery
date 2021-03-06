Before creating a PULL REQUEST or ISSUE
---

Please see https://github.com/coolaj86/node-jquery/issues/59

SOON TO BE TAKEN OVER BY JQUERY TEAM
====

When **jquery 2.x** is published to npm, it **will not be backwards compatible** with 1.x.

The jQuery team will be taking over `jQuery` and `jquery` on `npm`. In the meantime this repository still exists,
but `coolaj86` is not maintaining it or pushing new changes to npm.
See the discussion in the various issues to know who to contact about what.

DOES NOT WORK ON WINDOWS
====
Many people are having problems getting this module to work on windows. The
failure has to do with building contextify on window. It seems to be a windows
environment issue. I don't have access to a windows machine so I cannot explore
working through the windows install process. If you figure out how to build
[contextify](https://github.com/brianmcd/contextify) on windows please send me working instructions!

[![Build Status](https://api.travis-ci.org/coolaj86/node-jquery.png?branch=master)](https://travis-ci.org/coolaj86/node-jquery)

NPM module 'jQuery' (capital 'Q')
====

The is a browser CommonJS package for EnderJS, Pakmanager, etc.

    npm install jQuery


NPM module 'jquery' (lowercase 'q')
====

A stupid-simple wrapper over jQuery for  Node.JS (server). Currently 1.7.2.

Node.JS
---
```
    npm install jquery

    var $ = require('jquery').create();
```

Examples
---
```javascript
    $("<h1>test passes</h1>").appendTo("body");
    console.log($("body").html());
```

In Node.JS you may also create separate window instances

```javascript
    var jsdom = require('jsdom').jsdom
      , myWindow = jsdom().createWindow()
      , $ = require('jquery').create()
      , jQuery = require('jquery').create(myWindow)
      ;

    $("<h1>test passes</h1>").appendTo("body");
    console.log($("body").html());

    jQuery("<h3>second test passes</h3>").appendTo("body");
    console.log(jQuery("body").html());
```

Output:

```html
    <h1>test passes</h1>
    <h3>second test passes</h3>
```

You may also specify the version of jQuery you'd like to use
```javascript
    var $ = require('jquery')(null, '1.9');
```
Currently the version defaults to `1.8.3`.

Following versions are available -

* 1.6(.4)
* 1.7(.2)
* 1.8(.3)
* 1.9(.1)
* 2.0(.0)

JSONP Example
----

```javascript
    var $ = require('jquery');

    $.getJSON('http://twitter.com/status/user_timeline/treason.json?count=10&callback=?',function(data) {
      console.log(data);
    });
```

Building/Publishing to NPM
----
```
grunt && npm publish
```
