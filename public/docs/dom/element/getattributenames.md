Element.getAttributeNames()
===========================

The `getAttributeNames()` method of the [`Element`](../element) interface returns the attribute names of the element as an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of strings. If the element has no attributes it returns an empty array.

Using `getAttributeNames()` along with [`getAttribute()`](getattribute), is a memory-efficient and performant alternative to accessing [`Element.attributes`](attributes).

Syntax
------

    let attributeNames = element.getAttributeNames();

Example
-------

    // Iterate over element's attributes
    for (let name of element.getAttributeNames()) {
      let value = element.getAttribute(name);
      console.log(name, value);
    }

Polyfill
--------

    if (Element.prototype.getAttributeNames == undefined) {
      Element.prototype.getAttributeNames = function () {
        var attributes = this.attributes;
        var length = attributes.length;
        var result = new Array(length);
        for (var i = 0; i < length; i++) {
          result[i] = attributes[i].name;
        }
        return result;
      };
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-getattributenames">DOM<br />
<span class="small">The definition of 'Element.getAttributeNames' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`getAttributeNames`

61

18

45

No

48

10.1

61

61

45

45

10.3

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNames" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNames</a>
