# Element: DOMActivate event

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `DOMActivate` event is fired at an element when it becomes active, such as when it is clicked on using the mouse or a keypress is used to navigate to it.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../mouseevent"><code>MouseEvent</code></a></td></tr></tbody></table>

## Examples

    <svg xmlns="http://www.w3.org/2000/svg" version="1.2" baseProfile="tiny"
         xmlns:ev="http://www.w3.org/2001/xml-events"
         width="6cm" height="5cm" viewBox="0 0 600 500">

      <desc>Example: invoke an ECMAScript function from a DOMActivate event</desc>

      <!-- ECMAScript to change the radius -->
      <script type="application/ecmascript"><![CDATA[
        function change(evt) {
          var circle = evt.target;
          var currentRadius = circle.getFloatTrait("r");
          if (currentRadius == 100)
            circle.setFloatTrait("r", currentRadius * 2);
          else
            circle.setFloatTrait("r", currentRadius * 0.5);
        }
      ]]></script>

      <!-- Act on each DOMActivate event -->
      <circle cx="300" cy="225" r="100" fill="red">
        <handler type="application/ecmascript" ev:event="DOMActivate"> change(evt); </handler>
      </circle>

      <text x="300" y="480" font-family="Verdana" font-size="35" text-anchor="middle">
        Activate the circle to change its size
      </text>
    </svg>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-DOMActivate">UI Events<br />
<span class="small">The definition of 'DOMActivate' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`DOMActivate_event`

Yes

79

Yes

No

No

Yes

?

Yes

Yes

No

?

Yes

## See also

- [`MouseEvent`](../mouseevent)
- [`mousedown`](mousedown_event)
- [`mouseup`](mouseup_event)
- [`mousemove`](mousemove_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/DOMActivate_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/DOMActivate_event</a>
