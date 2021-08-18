ResizeObserver.observe()
========================

The `observe()` method of the [`ResizeObserver`](../resizeobserver) interface starts observing the specified [`Element`](../element) or [`SVGElement`](../svgelement).

Syntax
------

    resizeObserver.observe(target, options);

### Parameters

`target`  
A reference to an [`Element`](../element) or [`SVGElement`](../svgelement) to be observed.

options <span class="badge inline optional">Optional</span>   
An options object allowing you to set options for the observation. Currently this only has one possible option that can be set:

`box`  
Sets which box model the observer will observe changes to. Possible values are `content-box` (the default), `border-box`, and `device-pixel-content-box`.

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

An `observe()` call with an options object would look like so:

    resizeObserver.observe(divElem, { box : 'border-box' });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/resize-observer/#dom-resizeobserver-observe">Resize Observer<br />
<span class="small">The definition of 'observe()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`observe`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserver/observe" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserver/observe</a>
