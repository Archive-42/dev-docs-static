HTMLMarqueeElement
==================

**Draft**

This page is not complete.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `HTMLMarqueeElement` interface provides methods to manipulate [`<marquee>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/marquee) elements. It inherits properties and methods from the [`HTMLElement`](htmlelement) interface.

Properties
----------

*Inherits properties from its parent, [`HTMLElement`](htmlelement).*

<span class="page-not-created">`HTMLMarqueeElement.behavior`</span>  
Sets how the text is scrolled within the marquee. Possible values are `scroll`, `slide` and `alternate`. If no value is specified, the default value is `scroll`.

<span class="page-not-created">`HTMLMarqueeElement.bgColor`</span>  
Sets the background color through color name or hexadecimal value.

<span class="page-not-created">`HTMLMarqueeElement.direction`</span>  
Sets the direction of the scrolling within the marquee. Possible values are `left`, `right`, `up` and `down`. If no value is specified, the default value is `left`.

<span class="page-not-created">`HTMLMarqueeElement.height`</span>  
Sets the height in pixels or percentage value.

<span class="page-not-created">`HTMLMarqueeElement.hspace`</span>  
Sets the horizontal margin.

<span class="page-not-created">`HTMLMarqueeElement.loop`</span>  
Sets the number of times the marquee will scroll. If no value is specified, the default value is −1, which means the marquee will scroll continuously.

<span class="page-not-created">`HTMLMarqueeElement.scrollAmount`</span>  
Sets the amount of scrolling at each interval in pixels. The default value is 6.

<span class="page-not-created">`HTMLMarqueeElement.scrollDelay`</span>  
Sets the interval between each scroll movement in milliseconds. The default value is 85. Note that any value smaller than 60 is ignored and the value 60 is used instead, unless `trueSpeed` is `true`.

<span class="page-not-created">`HTMLMarqueeElement.trueSpeed`</span>  
By default, `scrollDelay` values lower than 60 are ignored. If `trueSpeed` is `true`, then those values are not ignored.

<span class="page-not-created">`HTMLMarqueeElement.vspace`</span>  
Sets the vertical margin.

<span class="page-not-created">`HTMLMarqueeElement.width`</span>  
Sets the width in pixels or percentage value.

### Event handlers

<span class="page-not-created">`HTMLMarqueeElement.onbounce`</span>  
Fires when the marquee has reached the end of its scroll position. It can only fire when the behavior attribute is set to `alternate`.

<span class="page-not-created">`HTMLMarqueeElement.onfinish`</span>  
Fires when the marquee has finished the amount of scrolling that is set by the loop attribute. It can only fire when the loop attribute is set to some number that is greater than 0.

<span class="page-not-created">`HTMLMarqueeElement.onstart`</span>  
Fires when the marquee starts scrolling.

Methods
-------

*Inherits methods from its parent, [`HTMLElement`](htmlelement).*

<span class="page-not-created">`HTMLMarqueeElement.start()`</span>  
Starts scrolling of the marquee.

<span class="page-not-created">`HTMLMarqueeElement.stop()`</span>  
Stops scrolling of the marquee.

Examples
--------

    <marquee>This text will scroll from right to left</marquee>

    <marquee direction="up">This text will scroll from bottom to top</marquee>

    <marquee direction="down" width="250" height="200" behavior="alternate" style="border:solid">
      <marquee behavior="alternate">
        This text will bounce
      </marquee>
    </marquee>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/obsolete.html#htmlmarqueeelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMarqueeElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Made obsolete in favor of CSS but define its expected behavior for backward compatibility.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/obsolete.html#htmlmarqueeelement">HTML 5.2<br />
<span class="small">The definition of 'HTMLMarqueeElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No changes.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html51/obsolete.html#htmlmarqueeelement-htmlmarqueeelement">HTML 5.1<br />
<span class="small">The definition of 'HTMLMarqueeElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No changes.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/obsolete.html#htmlmarqueeelement">HTML5<br />
<span class="small">The definition of 'HTMLMarqueeElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Made obsolete in favor of CSS but define its expected behavior for backward compatibility.</td></tr></tbody></table>

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

`HTMLMarqueeElement`

1

12

65

Before Firefox 65, `<marquee>` implemented the `HTMLDivElement` interface.

2

7.2

1.2

1

18

65

Before Firefox 65, `<marquee>` implemented the `HTMLDivElement` interface.

10.1

1

1.0

`behavior`

1

12

65

2

7.2

5.1

1

18

65

10.1

5

1.0

`bgColor`

1

12

65

2

7.2

3

1

18

65

10.1

1

1.0

`direction`

1

12

65

2

7.2

5.1

1

18

65

10.1

5

1.0

`height`

1

12

65

2

7.2

5.1

1

18

65

10.1

5

1.0

`hspace`

10

12

65

5.5

≤12.1

5.1

≤37

18

65

≤12.1

5

1.0

`loop`

10

12

65

5.5

≤12.1

5.1

≤37

18

65

≤12.1

5

1.0

`onbounce`

No

12-79

65

5.5

No

No

No

No

65

No

No

No

`onfinish`

No

12-79

65

5.5

No

No

No

No

65

No

No

No

`onstart`

No

12-79

65

5.5

No

No

No

No

65

No

No

No

`scrollAmount`

1

12

65

2

7.2

3

1

18

65

10.1

1

1.0

`scrollDelay`

10

12

65

5.5

≤12.1

5.1

1

18

65

≤12.1

6

1.0

`start`

1

12

65

5.5

≤12.1

1.2

1

18

65

≤12.1

1

1.0

`stop`

1

12

65

5.5

≤12.1

1.2

1

18

65

≤12.1

1

1.0

`trueSpeed`

Yes

12

65

4

Yes

No

Yes

Yes

65

Yes

No

Yes

`vspace`

10

12

65

5.5

≤12.1

5.1

≤37

18

65

≤12.1

5

1.0

`width`

1

12

65

2

7.2

5.1

1

18

65

10.1

5

1.0

See also
--------

-   [`<marquee>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/marquee)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMarqueeElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMarqueeElement</a>
