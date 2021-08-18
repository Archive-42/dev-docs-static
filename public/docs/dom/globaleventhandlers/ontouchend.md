GlobalEventHandlers.ontouchend
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `ontouchstart` is a [global event handler](../globaleventhandlers) for the `touchend` event.

**Note:** This property has *not* been formally standardized. It is specified in the [Touch Events – Level 2](https://w3c.github.io/touch-events/) <span class="spec-draft">Draft</span> specification and not in [Touch Events](https://www.w3.org/TR/touch-events/) <span class="spec-rec">Recommendation</span>. This property is not widely implemented.

Syntax
------

    var endHandler = targetElement.ontouchend;

### Return value

`endHandler`  
The `touchend` event handler for element `targetElement`.

Example
-------

This example shows two ways to use `ontouchend` to set an element's `touchend` event handler.

    <html>
    <script>
    function endTouch(ev) {
      // Process the event
    }
    function init() {
      let el = document.getElementById('target1');
      el.ontouchend = endTouch;
    }
    </script>

    <body onload="init();">
      <div id="target1"> Touch me ... </div>
      <div id="target2" ontouchend="endTouch(event)"> Touch me ... </div>
    </body>
    </html>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#dom-globaleventhandlers-ontouchend">Touch Events – Level 2</a></td><td><span class="spec-draft">Draft</span></td><td>Non-stable version.</td></tr></tbody></table>

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

`ontouchend`

No

No

No

No

No

No

≤37

18

Yes

≤14

≤3

1.0

See also
--------

-   `touchend`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchend" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchend</a>
