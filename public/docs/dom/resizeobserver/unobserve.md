ResizeObserver.unobserve()
==========================

The `unobserve()` method of the [`ResizeObserver`](../resizeobserver) interface ends the observing of a specified [`Element`](../element) or [`SVGElement`](../svgelement).

Syntax
------

    void unobserve(target);

### Parameters

`target`  
A reference to an [`Element`](../element) or [`SVGElement`](../svgelement) to be unobserved.

### Return value

Void.

### Exceptions

None.

Examples
--------

The following snippet is taken from the [resize-observer-text.html](https://mdn.github.io/dom-examples/resize-observer/resize-observer-text.html) ([see source](https://github.com/mdn/dom-examples/blob/master/resize-observer/resize-observer-text.html)) example:

    const resizeObserver = new ResizeObserver(entries => {
      for (let entry of entries) {
        if(entry.contentBoxSize) {
          // Checking for chrome as using a non-standard array
          if (entry.contentBoxSize[0]) {
            h1Elem.style.fontSize = Math.max(1.5, entry.contentBoxSize[0].inlineSize/200) + 'rem';
            pElem.style.fontSize = Math.max(1, entry.contentBoxSize[0].inlineSize/600) + 'rem';
          } else {
            h1Elem.style.fontSize = Math.max(1.5, entry.contentBoxSize.inlineSize/200) + 'rem';
            pElem.style.fontSize = Math.max(1, entry.contentBoxSize.inlineSize/600) + 'rem';
          }
        } else {
          h1Elem.style.fontSize = Math.max(1.5, entry.contentRect.width/200) + 'rem';
          pElem.style.fontSize = Math.max(1, entry.contentRect.width/600) + 'rem';
        }
      }
      console.log('Size changed');
    });

    resizeObserver.observe(divElem);

    checkbox.addEventListener('change', () => {
      if(checkbox.checked) {
        resizeObserver.observe(divElem);
      } else {
        resizeObserver.unobserve(divElem);
      }
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/resize-observer/#dom-resizeobserver-unobserve">Resize Observer<br />
<span class="small">The definition of 'unobserve()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`unobserve`

64

79

69

No

51

13.1

64

64

79

47

13.4

9.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserver/unobserve" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserver/unobserve</a>
