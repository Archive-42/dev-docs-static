&lt;marquee&gt;: The Marquee element
====================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The HTML `<marquee>` element is used to insert a scrolling area of text. You can control what happens when the text reaches the edges of its content area using its attributes.

<table><tbody><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMarqueeElement"><code>HTMLMarqueeElement</code></a></td></tr></tbody></table>

Attributes
----------

`behavior`  
Sets how the text is scrolled within the marquee. Possible values are `scroll`, `slide` and `alternate`. If no value is specified, the default value is `scroll`.

`bgcolor`  
Sets the background color through color name or hexadecimal value.

`direction`  
Sets the direction of the scrolling within the marquee. Possible values are `left`, `right`, `up` and `down`. If no value is specified, the default value is `left`.

`height`  
Sets the height in pixels or percentage value.

`hspace`  
Sets the horizontal margin

`loop`  
Sets the number of times the marquee will scroll. If no value is specified, the default value is −1, which means the marquee will scroll continuously.

`scrollamount`  
Sets the amount of scrolling at each interval in pixels. The default value is 6.

`scrolldelay`  
Sets the interval between each scroll movement in milliseconds. The default value is 85. Note that any value smaller than 60 is ignored and the value 60 is used instead, unless` truespeed `is specified.

`truespeed`  
By default,` scrolldelay `values lower than 60 are ignored. If` truespeed `is present, those values are not ignored.

`vspace`  
Sets the vertical margin in pixels or percentage value.

`width`  
Sets the width in pixels or percentage value.

Event handlers
--------------

`onbounce`  
Fires when the marquee has reached the end of its scroll position. It can only fire when the behavior attribute is set to `alternate`.

`onfinish`  
Fires when the marquee has finished the amount of scrolling that is set by the loop attribute. It can only fire when the loop attribute is set to some number that is greater than 0.

`onstart`  
Fires when the marquee starts scrolling.

Methods
-------

`start()`  
Starts scrolling of the marquee.

`stop()`  
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/obsolete.html#the-marquee-element-2">HTML Living Standard<br />
<span class="small">The definition of '&lt;marquee&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Make it obsolete in favor of CSS but define its expected behavior, for backward compatibility. However, the development of the marquee features of CSS have since been <a href="https://www.w3.org/TR/css3-marquee/">abandoned</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/obsolete.html#the-marquee-element-0">HTML5<br />
<span class="small">The definition of '&lt;marquee&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Make it obsolete in favor of CSS but define its expected behavior, for backward compatibility. However, the development of the marquee features of CSS have since been <a href="https://www.w3.org/TR/css3-marquee/">abandoned</a>.</td></tr></tbody></table>

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

`marquee`

1

12

65

1

Implements the `HTMLDivElement` interface.

2

7.2

1.2

1

18

65

4

Implements the `HTMLDivElement` interface.

10.1

Yes

1.0

`behavior`

1

12

1

2

7.2

1.2

1

18

4

10.1

Yes

1.0

`bgcolor`

1

12

1

2

7.2

1.2

1

18

4

10.1

Yes

1.0

`direction`

1

12

1

2

7.2

1.2

1

18

4

10.1

Yes

1.0

`height`

1

12

1

2

7.2

1.2

1

18

4

10.1

Yes

1.0

`hspace`

Yes

≤18

3

?

Yes

?

Yes

Yes

4

Yes

?

Yes

`loop`

Yes

≤18

3

?

Yes

?

Yes

Yes

4

Yes

?

Yes

`scrollamount`

1

12

1

2

7.2

1.2

1

18

4

10.1

Yes

1.0

`scrolldelay`

1

12

1

2

7.2

1.2

1

18

4

10.1

Yes

1.0

`truespeed`

Yes

12

3

4

Yes

No

Yes

Yes

4

Yes

No

Yes

`vspace`

Yes

≤18

3

?

Yes

?

Yes

Yes

4

Yes

?

Yes

`width`

1

12

1

2

7.2

1.2

1

18

4

10.1

Yes

1.0

See also
--------

-   [`HTMLMarqueeElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMarqueeElement)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/marquee" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/marquee</a>
