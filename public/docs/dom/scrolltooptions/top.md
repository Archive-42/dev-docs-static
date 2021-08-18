ScrollToOptions.top
===================

The `top` property of the [`ScrollToOptions`](../scrolltooptions) dictionary specifies the number of pixels along the Y axis to scroll the window or element.

Syntax
------

    top: double

### Value

A double.

Examples
--------

In our [scrolltooptions example](https://github.com/mdn/dom-examples/tree/master/scrolltooptions) ([see it live](https://mdn.github.io/dom-examples/scrolltooptions/)) we include a form that allows the user to enter three values — two numbers representing the left and top properties (i.e. the positions to scroll to along the X and Y axes), and a checkbox indicating whether they want smooth scrolling enabled or not.

When the form is submitted, an event handler is run that puts the entered values into a ScrollToOptions dictionary, and then invokes the [`Window.ScrollTo()`](../window/scrollto) method, passing the dictionary as a parameter:

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-scrolltooptions-top">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'top' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

See also
--------

[`ScrollToOptions`](../scrolltooptions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ScrollToOptions/top" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ScrollToOptions/top</a>
