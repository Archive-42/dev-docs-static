Element.setAttribute()
======================

Sets the value of an attribute on the specified element. If the attribute already exists, the value is updated; otherwise a new attribute is added with the specified name and value.

To get the current value of an attribute, use [`getAttribute()`](getattribute); to remove an attribute, call [`removeAttribute()`](removeattribute).

Syntax
------

    Element.setAttribute(name, value);

### Parameters

`name`  
A [`DOMString`](../domstring) specifying the name of the attribute whose value is to be set. The attribute name is automatically converted to all lower-case when `setAttribute()` is called on an HTML element in an HTML document.

`value`  
A [`DOMString`](../domstring) containing the value to assign to the attribute. Any non-string value specified is converted automatically into a string.

Boolean attributes are considered to be `true` if they're present on the element at all, regardless of their actual `value`; as a rule, you should specify the empty string (`""`) in `value` (some people use the attribute's name; this works but is non-standard). See the [example](#example) below for a practical demonstration.

Since the specified `value` gets converted into a string, specifying `null` doesn't necessarily do what you expect. Instead of removing the attribute or setting its value to be [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null), it instead sets the attribute's value to the string `"null"`. If you wish to remove an attribute, call [`removeAttribute()`](removeattribute).

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Exceptions

`InvalidCharacterError`  
The specified attribute `name` contains one or more characters which are not valid in attribute names.

Example
-------

In the following example, `setAttribute()` is used to set attributes on a [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button).

### HTML

    <button>Hello World</button>

### JavaScript

    var b = document.querySelector("button");

    b.setAttribute("name", "helloButton");
    b.setAttribute("disabled", "");

This demonstrates two things:

-   The first call to `setAttribute()` above shows changing the `name` attribute's value to "helloButton". You can see this using your browser's page inspector ([Chrome](https://developers.google.com/web/tools/chrome-devtools/inspect-styles), [Edge](https://docs.microsoft.com/en-us/microsoft-edge/f12-devtools-guide/dom-explorer), [Firefox](https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector), [Safari](https://developer.apple.com/library/content/documentation/AppleApplications/Conceptual/Safari_Developer_Guide/Introduction/Introduction.html)).
-   To set the value of a Boolean attribute, such as `disabled`, you can specify any value. An empty string or the name of the attribute are recommended values. All that matters is that if the attribute is present at all, *regardless of its actual value*, its value is considered to be `true`. The absence of the attribute means its value is `false`. By setting the value of the `disabled` attribute to the empty string (`""`), we are setting `disabled` to `true`, which results in the button being disabled.

DOM methods dealing with element's attributes:

<table><thead><tr class="header"><th>Not namespace-aware, most commonly used methods</th><th>Namespace-aware variants (DOM Level 2)</th><th>DOM Level 1 methods for dealing with <code>Attr</code> nodes directly (seldom used)</th><th>DOM Level 2 namespace-aware methods for dealing with <code>Attr</code> nodes directly (seldom used)</th></tr></thead><tbody><tr class="odd"><td><a href="setattribute"><code>setAttribute</code></a> (DOM 1)</td><td><a href="setattributens"><code>setAttributeNS</code></a></td><td><a href="setattributenode"><code>setAttributeNode</code></a></td><td><a href="setattributenodens"><code>setAttributeNodeNS</code></a></td></tr><tr class="even"><td><a href="getattribute"><code>getAttribute</code></a> (DOM 1)</td><td><a href="getattributens"><code>getAttributeNS</code></a></td><td><a href="getattributenode"><code>getAttributeNode</code></a></td><td><a href="getattributenodens"><code>getAttributeNodeNS</code></a></td></tr><tr class="odd"><td><a href="hasattribute"><code>hasAttribute</code></a> (DOM 2)</td><td><a href="hasattributens"><code>hasAttributeNS</code></a></td><td>-</td><td>-</td></tr><tr class="even"><td><a href="removeattribute"><code>removeAttribute</code></a> (DOM 1)</td><td><a href="removeattributens"><code>removeAttributeNS</code></a></td><td><a href="removeattributenode"><code>removeAttributeNode</code></a></td><td>-</td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-setattribute">DOM<br />
<span class="small">The definition of 'setAttribute()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`setAttribute`

1

12

1

5

In Internet Explorer 7 and earlier, `setAttribute` doesn't set styles and removes events when you try to set them.

8

1

1

18

4

10.1

1

1.0

### Gecko notes

Using `setAttribute()` to modify certain attributes, most notably `value` in XUL, works inconsistently, as the attribute specifies the default value. To access or modify the current values, you should use the properties. For example, use `Element.value` instead of `Element.setAttribute()`.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute</a>
