Element.toggleAttribute()
=========================

The `toggleAttribute()` method of the [`Element`](../element) interface toggles a Boolean attribute (removing it if it is present and adding it if it is not present) on the given element.

Syntax
------

    Element.toggleAttribute(name [, force]);

### Parameters

`name`  
A [`DOMString`](../domstring) specifying the name of the attribute to be toggled. The attribute name is automatically converted to all lower-case when `toggleAttribute()` is called on an HTML element in an HTML document.

 `force` <span class="badge inline optional">Optional</span>   
A boolean value to determine whether the attribute should be added or removed, no matter whether the attribute is present or not at the moment.

### Return value

`true` if attribute `name` is eventually present, and `false` otherwise.

### Exceptions

`InvalidCharacterError`  
The specified attribute `name` contains one or more characters which are not valid in attribute names.

Example
-------

In the following example, `toggleAttribute()` is used to toggle the `disabled` attribute of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input).

### HTML

    <input value="text">
    <button>toggleAttribute("disabled")</button>

### JavaScript

    var button = document.querySelector("button");
    var input = document.querySelector("input");

    button.addEventListener("click", function(){
      input.toggleAttribute("disabled");
    });

### Result

DOM methods dealing with element's attributes:

<table><thead><tr class="header"><th>Not namespace-aware, most commonly used methods</th><th>Namespace-aware variants (DOM Level 2)</th><th>DOM Level 1 methods for dealing with <code>Attr</code> nodes directly (seldom used)</th><th>DOM Level 2 namespace-aware methods for dealing with <code>Attr</code> nodes directly (seldom used)</th></tr></thead><tbody><tr class="odd"><td><a href="setattribute"><code>setAttribute</code></a> (DOM 1)</td><td><a href="setattributens"><code>setAttributeNS</code></a></td><td><a href="setattributenode"><code>setAttributeNode</code></a></td><td><a href="setattributenodens"><code>setAttributeNodeNS</code></a></td></tr><tr class="even"><td><a href="getattribute"><code>getAttribute</code></a> (DOM 1)</td><td><a href="getattributens"><code>getAttributeNS</code></a></td><td><a href="getattributenode"><code>getAttributeNode</code></a></td><td><a href="getattributenodens"><code>getAttributeNodeNS</code></a></td></tr><tr class="odd"><td><a href="hasattribute"><code>hasAttribute</code></a> (DOM 2)</td><td><a href="hasattributens"><code>hasAttributeNS</code></a></td><td>-</td><td>-</td></tr><tr class="even"><td><a href="removeattribute"><code>removeAttribute</code></a> (DOM 1)</td><td><a href="removeattributens"><code>removeAttributeNS</code></a></td><td><a href="removeattributenode"><code>removeAttributeNode</code></a></td><td>-</td></tr></tbody></table>

Polyfill
--------

    if (!Element.prototype.toggleAttribute) {
      Element.prototype.toggleAttribute = function(name, force) {
        if(force !== void 0) force = !!force

        if (this.hasAttribute(name)) {
          if (force) return true;

          this.removeAttribute(name);
          return false;
        }
        if (force === false) return false;

        this.setAttribute(name, "");
        return true;
      };
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-toggleattribute">DOM<br />
<span class="small">The definition of 'Element.toggleAttribute' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`toggleAttribute`

69

18

63

No

56

12

69

69

63

48

Yes

10.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/toggleAttribute" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/toggleAttribute</a>
