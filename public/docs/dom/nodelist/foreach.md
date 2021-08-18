NodeList.prototype.forEach()
============================

The `forEach()` method of the [`NodeList`](../nodelist) interface calls the callback given in parameter once for each value pair in the list, in insertion order.

Syntax
------

    someNodeList.forEach(callback[, thisArg]);

### Parameters

`callback`  
A function to execute on each element of `someNodeList`. It accepts 3 parameters:

`currentValue`  
The current element being processed in `someNodeList`.

 `currentIndex` <span class="badge inline optional">Optional</span>   
The index of the `currentValue` being processed in `someNodeList`.

 `listObj` <span class="badge inline optional">Optional</span>   
The `someNodeList` that `forEach()` is being applied to.

 `thisArg` <span class="badge inline optional">Optional</span>   
Value to use as `this` when executing `callback`.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

Example
-------

    let node = document.createElement("div");
    let kid1 = document.createElement("p");
    let kid2 = document.createTextNode("hey");
    let kid3 = document.createElement("span");

    node.appendChild(kid1);
    node.appendChild(kid2);
    node.appendChild(kid3);

    let list = node.childNodes;

    list.forEach(
      function(currentValue, currentIndex, listObj) {
        console.log(currentValue + ', ' + currentIndex + ', ' + this);
      },
      'myThisArg'
    );

The above code results in the following:

    [object HTMLParagraphElement], 0, myThisArg
    [object Text], 1, myThisArg
    [object HTMLSpanElement], 2, myThisArg

Polyfill
--------

This [polyfill](https://developer.mozilla.org/en-US/docs/Glossary/Polyfill) adds compatibility to all Browsers supporting [ES5](https://caniuse.com/#search=es5):

    if (window.NodeList && !NodeList.prototype.forEach) {
        NodeList.prototype.forEach = function (callback, thisArg) {
            thisArg = thisArg || window;
            for (var i = 0; i < this.length; i++) {
                callback.call(thisArg, this[i], i, this);
            }
        };
    }

OR

    if (window.NodeList && !NodeList.prototype.forEach) {
       NodeList.prototype.forEach = Array.prototype.forEach;
    }

The above behavior is how many browsers actually implement `NodeList.prototype.forEach()` (Chrome, for example).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://heycam.github.io/webidl/#es-forEach">Web IDL<br />
<span class="small">The definition of 'forEach' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines <code>forEach</code> on <code>iterable</code> declarations</td></tr></tbody></table>

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`forEach`

51

16

50

No

38

10

51

51

50

41

10

5.0

See also
--------

-   [`Node`](../node)
-   [`NodeList`](../nodelist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NodeList/forEach" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NodeList/forEach</a>
