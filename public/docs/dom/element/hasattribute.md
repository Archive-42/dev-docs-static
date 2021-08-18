# Element.hasAttribute()

The `Element.hasAttribute()` method returns a **Boolean** value indicating whether the specified element has the specified attribute or not.

## Syntax

    var result = element.hasAttribute(name);

`result`  
holds the return value `true` or `false`.

`name`  
is a string representing the name of the attribute.

## Example

    var foo = document.getElementById("foo");
    if (foo.hasAttribute("bar")) {
        // do something
    }

## Polyfill

    ;(function(prototype) {
        prototype.hasAttribute = prototype.hasAttribute || function(name) {
            return !!(this.attributes[name] &&
                      this.attributes[name].specified);
        }
    })(Element.prototype);

## Notes

DOM methods dealing with element's attributes:

<table><thead><tr class="header"><th>Not namespace-aware, most commonly used methods</th><th>Namespace-aware variants (DOM Level 2)</th><th>DOM Level 1 methods for dealing with <code>Attr</code> nodes directly (seldom used)</th><th>DOM Level 2 namespace-aware methods for dealing with <code>Attr</code> nodes directly (seldom used)</th></tr></thead><tbody><tr class="odd"><td><a href="setattribute"><code>setAttribute</code></a> (DOM 1)</td><td><a href="setattributens"><code>setAttributeNS</code></a></td><td><a href="setattributenode"><code>setAttributeNode</code></a></td><td><a href="setattributenodens"><code>setAttributeNodeNS</code></a></td></tr><tr class="even"><td><a href="getattribute"><code>getAttribute</code></a> (DOM 1)</td><td><a href="getattributens"><code>getAttributeNS</code></a></td><td><a href="getattributenode"><code>getAttributeNode</code></a></td><td><a href="getattributenodens"><code>getAttributeNodeNS</code></a></td></tr><tr class="odd"><td><a href="hasattribute"><code>hasAttribute</code></a> (DOM 2)</td><td><a href="hasattributens"><code>hasAttributeNS</code></a></td><td>-</td><td>-</td></tr><tr class="even"><td><a href="removeattribute"><code>removeAttribute</code></a> (DOM 1)</td><td><a href="removeattributens"><code>removeAttributeNS</code></a></td><td><a href="removeattributenode"><code>removeAttributeNode</code></a></td><td>-</td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-hasattribute">DOM<br />
<span class="small">The definition of 'Element.hasAttribute()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>From <a href="https://www.w3.org/TR/DOM-Level-3-Core/">Document Object Model (DOM) Level 3 Core Specification</a>, moved from <a href="../node"><code>Node</code></a> to <a href="../element"><code>Element</code></a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-ElHasAttr">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Element.hasAttribute()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Core/">Document Object Model (DOM) Level 2 Core Specification</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-ElHasAttr">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Element.hasAttribute()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`hasAttribute`

1

12

1

8

8

1

1

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/hasAttribute" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/hasAttribute</a>
