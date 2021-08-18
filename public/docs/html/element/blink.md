&lt;blink&gt;: The Blinking Text element
========================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The **HTML Blink Element** (`<blink>`) is a non-standard element which causes the enclosed text to flash slowly.

Do not use this element as it is **obsolete** and is bad design practice. Blinking text is frowned upon by several accessibility standards and the CSS specification allows browsers to ignore the `<blink>` element.

DOM interface
-------------

This element is unsupported and thus implements the [`HTMLUnknownElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLUnknownElement) interface.

Example
-------

    <blink>Why would somebody use this?</blink>

### Result (toned down!)

<img src="data:image/gif;base64,R0lGODlh1wAeANUsAP//v5zf/wAAAL///3S///+/dHQAAP//35xIAAAAdHQASP/fnL90AN///wBInAB0v0ic39+cSEgASEgAdAAASEgAAEhInHQAdHScnJxISEicnJy/nEhISJycdL//3790SHR0dN//39//v7//v7/fnJxIdL+/dJzfv9/f35zf30hIAP///////wAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAACH/C05FVFNDQVBFMi4wAwEAAAAh+QQFRgAsACwAAAAA1wAeAAAG/8CVcEgsGo/IpHLJbDqf0Kh0Sq1ar9isdsvter/gsHhMLpvP6LR6zW673/C4fE6v2+/4vH7P7x9RbAwPQwUCEEMRDiIGBGkACgFFj5Flk1KWZQcIhwCMkpBInQICCQNSiQ1CDCCDK5oQnY1omEO0Y7ZOuGGvK7FPmq0RpVELE6YHGScXppOdGBUCFJGCiK2uCI0LFY2omqMOqb4rBaWW3gIaoEQRo9JC5+ArxSajEIWGQwzf4Qodo8PX9r1DMCpdAGpCIljr5WncMHbRKK3QJyDekHMPnEFzZwmiO3Kmrsn6hU2ehRAliw3oNIwBOJAi1w0qwOEQAwjAVIETB9ISNf9N7gg9BJdzIjhtMwXMdIfQZQOWppwWdTpxENAAMDWNZCgLJExUVXWmuriJYcudkL5arNUQys1xhyLEHcSznCeVRAqAi8BKK16udVdCWiCBEmGJDkMK+RvrsLzCvQZDjhxAXGNjQhpPPuzrb+aGXgEunmyLV+BJMI90WvikwCAG2Sw0gM1VCExqCiUt+7DBgohlese+Op0WYGmCArpafOXYEupR0JNjehV8oD3joHCzDnyua/RRW02DLgepuyQDrJ8UG7Gs1wUPGSIFljfBQ0kiyFKUYE9CdvVrsIwnGFbYIZYPKQP8xxxkzhWnWGbqaKXgJqlZUox9W9WW2IGlpHb/hHhdkSeRPqKBNQUyvY3FAAayaZgVAhhgVkQELIaQQQeHMMYIcQE49piBbBGgo5AMgjKJj0FC2KOMmhkGmSYxPuiiaFwhaQSItolIhDgTHVIFAzUhEuaUIbGT3jj4fKBCI1MRhYBVCGgpFQJBZWnKYW020JyR2cVTgDSdxDNnK1TNGZSZV755TYfDOEbVn4hhmRhqjU6WRSEjaSPLfPJso5onwoQEz1iiULCBMZhQZFARFCU3kEB7yqcORRz1I1BAFY01UUHqaPppNKdGBd1ItAJpJo+7gkfEW2p45kcazj5LhlzSrkFttWRosxa22VawLbfghivuuOSWa+656KarEO667Lbr7rvwxivvvPTCGwQAIfkEBRQALAAsCAAIAMYADgAABkTAlXBILBqPyKRyyWw6n9CodEqtWq/YrHbL7Xq/4LB4TC6bz+i0es1uu9/wuHxOr9vv+Lx+z+/7/4CBgoOEhYaHiImHQQA7" width="215" height="30" />

Specifications
--------------

This element is non-standard and not part of any specification. If you don't believe us, [see for yourself in the HTML spec](https://html.spec.whatwg.org/multipage/obsolete.html#non-conforming-features).

CSS polyfill
------------

If you really do need a polyfill, then you can use the following CSS polyfill. Works in IE10+.

    blink {
      -webkit-animation: 2s linear infinite condemned_blink_effect; /* for Safari 4.0 - 8.0 */
      animation: 2s linear infinite condemned_blink_effect;
    }

    /* for Safari 4.0 - 8.0 */
    @-webkit-keyframes condemned_blink_effect {
      0% {
        visibility: hidden;
      }
      50% {
        visibility: hidden;
      }
      100% {
        visibility: visible;
      }
    }

    @keyframes condemned_blink_effect {
      0% {
        visibility: hidden;
      }
      50% {
        visibility: hidden;
      }
      100% {
        visibility: visible;
      }
    }

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

`blink`

No

No

1-22

No

2-15

No

No

No

4-22

10.1-14

No

No

See also
--------

-   [History of the creation of the HTML `<blink>` element](http://www.montulli.org/theoriginofthe%3Cblink%3Etag).
-   [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration), where a blink value exists, though browsers are not required to effectively make it blink.
-   [`<marquee>`](marquee), another similar non-standard element.
-   [CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations) are the way to go to create such an effect.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blink" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blink</a>
