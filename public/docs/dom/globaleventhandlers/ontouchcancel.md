# GlobalEventHandlers.ontouchcancel

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `ontouchcancel` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `touchcancel` events.

**Note:** This property has _not_ been formally standardized. It is specified in the [Touch Events – Level 2](https://w3c.github.io/touch-events/) <span class="spec-draft">Draft</span> specification and not in [Touch Events](https://www.w3.org/TR/touch-events/) <span class="spec-rec">Recommendation</span>. This property is not widely implemented.

## Syntax

    var cancelHandler = someElement.ontouchcancel;

### Return value

`cancelHandler`  
The `touchcancel` event handler for element `someElement`.

## Example

This example shows two ways to use `ontouchcancel` to set an element's `touchcancel` event handler.

    <html>
    <script>
    function cancelTouch(ev) {
      // Process the event
    }
    function init() {
      let el = document.getElementById('target1');
      el.ontouchcancel = cancelTouch;
    }
    </script>

    <body onload="init();">
      <div id="target1"> Touch me ... </div>
      <div id="target2" ontouchcancel="cancelTouch(event)"> Touch me ... </div>
    </body>
    </html>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#dom-globaleventhandlers-ontouchcancel">Touch Events – Level 2</a></td><td><span class="spec-draft">Draft</span></td><td>Non-stable version.</td></tr></tbody></table>

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

`ontouchcancel`

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

## See also

- `touchcancel`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchcancel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/ontouchcancel</a>
