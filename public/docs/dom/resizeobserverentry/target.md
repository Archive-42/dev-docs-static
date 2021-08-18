ResizeObserverEntry.target
==========================

The `target` read-only property of the [`ResizeObserverEntry`](../resizeobserverentry) interface returns a reference to the [`Element`](../element) or [`SVGElement`](../svgelement) that is being observed.

Syntax
------

    var element = ResizeObserverEntry.target;
    var svgElement = ResizeObserverEntry.target;

### Value

An [`Element`](../element) or [`SVGElement`](../svgelement) representing the element being observed.

Examples
--------

The following snippet is taken from the [resize-observer-border-radius.html](https://mdn.github.io/dom-examples/resize-observer/resize-observer-border-radius.html) ([see source](https://github.com/mdn/dom-examples/blob/master/resize-observer/resize-observer-border-radius.html)) example. This example includes a green box, sized as a percentage of the viewport size. When the viewport size is changed, the box's rounded corners change in proportion to the size of the box. We could just implement this using [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) with a percentage, but that quickly leads to ugly-looking elliptical corners; this solution gives you nice square corners that scale with the box size.

To grab a reference to the observed element so we can update its [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) value after each change, we make use of the `target` property of each entry — `entry.target.style.borderRadius`.

    const resizeObserver = new ResizeObserver(entries => {
      for (let entry of entries) {
        if(entry.contentBoxSize) {
          entry.target.style.borderRadius = Math.min(100, (entry.contentBoxSize.inlineSize/10) +
                                                          (entry.contentBoxSize.blockSize/10)) + 'px';
        } else {
          entry.target.style.borderRadius = Math.min(100, (entry.contentRect.width/10) +
                                                          (entry.contentRect.height/10)) + 'px';
        }
      }
    });

    resizeObserver.observe(document.querySelector('div'));

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/resize-observer/#dom-resizeobserverentry-target">Resize Observer<br />
<span class="small">The definition of 'target' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`target`

64

79

69

No

Yes

No

64

64

No

Yes

No

9.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserverEntry/target" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserverEntry/target</a>
