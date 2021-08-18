# Element.hasAttributes()

The `hasAttributes()` method of the [`Element`](../element) interface returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the current element has any attributes or not.

## Syntax

    var result = element.hasAttributes();

### Return value

`result`  
holds the return value `true` or `false`.

## Examples

    let foo = document.getElementById('foo');
    if (foo.hasAttributes()) {
      // Do something with 'foo.attributes'
    }

## Polyfill

    ;(function(prototype) {
      prototype.hasAttributes = prototype.hasAttributes || function() {
        return (this.attributes.length > 0);
      }
    })(Element.prototype);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-hasattributes">DOM<br />
<span class="small">The definition of 'Element.hasAttributes()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Moved from the <a href="../node"><code>Node</code></a> interface to the more specialized <a href="../element"><code>Element</code></a> interface.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/#ID-NodeHasAttrs">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'hasAttributes()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Core/">Document Object Model (DOM) Level 2 Core Specification</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/#ID-NodeHasAttrs">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'hasAttributes()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition, on the <a href="../node"><code>Node</code></a> interface.</td></tr></tbody></table>

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

`hasAttributes`

1

12

1

Before Firefox 35, it was implemented on the `Node` interface.

8

≤12.1

1

1

18

4

Before Firefox 35, it was implemented on the `Node` interface.

≤12.1

1

1.0

## See also

- [`Element.attributes`](attributes)
- [`Element.hasAttribute()`](hasattribute)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/hasAttributes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/hasAttributes</a>
