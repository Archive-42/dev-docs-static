# DOMTokenList.forEach()

The `forEach()` method of the [`DOMTokenList`](../domtokenlist) interface calls the callback given in parameter once for each value pair in the list, in insertion order.

## Syntax

    tokenList.forEach(callback [, thisArg]);

### Parameters

`callback`  
Function to execute for each element, eventually taking three arguments:

`currentValue`  
The current element being processed in the array.

`currentIndex`  
The index of the current element being processed in the array.

`listObj`  
The array that `forEach()` is being applied to.

`thisArg` <span class="badge inline optional">Optional</span>  
Value to use as [`this`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this) when executing `callback`.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

## Example

In the following example we retrieve the list of classes set on a [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) element as a `DOMTokenList` using [`Element.classList`](../element/classlist). We when retrieve an iterator containing the values using `forEach()`, writing each one to the `<span>`'s [`Node.textContent`](../node/textcontent) inside the `forEach()` inner function.

### HTML

    <span class="a b c"></span>

### JavaScript

    let span = document.querySelector("span");
    let classes = span.classList;
    let iterator = classes.values();

    classes.forEach(
      function(value, key, listObj) {
        span.textContent += `${value}${key}/${this}  ++  `;
      },
      "arg"
    );

### Result

## Polyfill

This [polyfill](https://developer.mozilla.org/en-US/docs/Glossary/Polyfill) adds compatibility to all Browsers supporting [ES5](https://caniuse.com/#search=es5):

    if (window.DOMTokenList && !DOMTokenList.prototype.forEach) {
      DOMTokenList.prototype.forEach = function (callback, thisArg) {
        thisArg = thisArg || window;
        for (var i = 0; i < this.length; i++) {
          callback.call(thisArg, this[i], i, this);
        }
      };
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#domtokenlist">DOM<br />
<span class="small">The definition of 'forEach() (as iterable&lt;Node&gt;)' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

42

16

50

No

32

10.1

45

45

50

32

10.3

5.0

## See also

- <span class="page-not-created">`DOMSettableTokenList`</span> (object that extends DOMTokenList with settable _.value_ property)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/forEach" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/forEach</a>
