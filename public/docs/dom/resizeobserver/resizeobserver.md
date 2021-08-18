# ResizeObserver()

The `ResizeObserver` constructor creates a new [`ResizeObserver`](../resizeobserver) object, which can be used to report changes to the content or border box of an [`Element`](../element) or the bounding box of an [`SVGElement`](../svgelement).

## Syntax

    var ResizeObserver = new ResizeObserver(callback)

### Parameters

`callback`  
The function called whenever an observed resize occurs. The function is called with two parameters:

`entries`  
An array of [`ResizeObserverEntry`](../resizeobserverentry) objects that can be used to access the new dimensions of the element after each change.

`observer`  
A reference to the `ResizeObserver` itself, so it will definitely be accessible from inside the callback, should you need it. This could be used for example to automatically unobserve the observer when a certain condition is reached, but you can omit it if you don't need it.

The callback will generally follow a pattern along the lines of:

    function(entries, observer) {
      for (let entry of entries) {
        // Do something to each entry
        // and possibly something to the observer itself
      }
    }

## Examples

The following snippet is taken from the [resize-observer-text.html](https://mdn.github.io/dom-examples/resize-observer/resize-observer-text.html) ([see source](https://github.com/mdn/dom-examples/blob/master/resize-observer/resize-observer-text.html)) example:

    const resizeObserver = new ResizeObserver(entries => {
      for (let entry of entries) {
        if(entry.contentBoxSize) {
          if (entry.contentBoxSize[0]) {
            h1Elem.style.fontSize = Math.max(1.5, entry.contentBoxSize[0].inlineSize/200) + 'rem';
            pElem.style.fontSize = Math.max(1, entry.contentBoxSize[0].inlineSize/600) + 'rem';
          } else {
            // legacy path
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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/resize-observer/#dom-resizeobserver-resizeobserver">Resize Observer<br />
<span class="small">The definition of 'ResizeObserver' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ResizeObserver`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserver/ResizeObserver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserver/ResizeObserver</a>
