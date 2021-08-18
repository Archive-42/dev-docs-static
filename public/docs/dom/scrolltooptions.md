ScrollToOptions
===============

The `ScrollToOptions` dictionary of the CSSOM View spec contains properties specifying where an element should be scrolled to, and whether the scrolling should be smooth.

A `ScrollToOptions` dictionary can be provided as a parameter for the following methods:

-   [`Window.scroll()`](window/scroll)
-   [`Window.scrollBy()`](window/scrollby)
-   [`Window.scrollTo()`](window/scrollto)
-   [`Element.scroll()`](element/scroll)
-   [`Element.scrollBy()`](element/scrollby)
-   [`Element.scrollTo()`](element/scrollto)

Properties
----------

[`ScrollToOptions.top`](scrolltooptions/top)  
Specifies the number of pixels along the Y axis to scroll the window or element.

[`ScrollToOptions.left`](scrolltooptions/left)  
Specifies the number of pixels along the X axis to scroll the window or element.

[`ScrollToOptions.behavior`](scrolltooptions/behavior)  
Specifies whether the scrolling should animate smoothly, or happen instantly in a single jump. This is actually defined on the `ScrollOptions` dictionary, which is implemented by `ScrollToOptions`.

Examples
--------

In our [scrolltooptions example](https://github.com/mdn/dom-examples/tree/master/scrolltooptions) ([see it live](https://mdn.github.io/dom-examples/scrolltooptions/)) we include a form that allows the user to enter three values — two numbers representing the left and top properties (i.e. the positions to scroll to along the X and Y axes), and a checkbox indicating whether they want smooth scrolling enabled or not.

When the form is submitted, an event handler is run that puts the entered values into a ScrollToOptions dictionary, and then invokes the [`Window.ScrollTo()`](window/scrollto) method, passing the dictionary as a parameter:

    form.addEventListener('submit', (e) => {
      e.preventDefault();
      var scrollOptions = {
        left: leftInput.value,
        top: topInput.value,
        behavior: scrollInput.checked ? 'smooth' : 'auto'
      }

      window.scrollTo(scrollOptions);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dictdef-scrolltooptions">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'ScrollToOptions' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`ScrollToOptions`

45

79

Yes

No

32

Yes

45

45

Yes

32

Yes

5.0

`behavior`

45

79

Yes

No

32

Yes

Safari does not have support for the `smooth` scroll behavior.

45

45

Yes

32

Yes

Safari does not have support for the `smooth` scroll behavior.

5.0

`left`

45

79

Yes

No

32

Yes

45

45

Yes

32

Yes

5.0

`top`

45

79

Yes

No

32

Yes

45

45

Yes

32

Yes

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ScrollToOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ScrollToOptions</a>
