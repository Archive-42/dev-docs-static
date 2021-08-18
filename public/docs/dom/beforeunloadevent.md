# BeforeUnloadEvent

The `beforeunload` event is fired when the window, the document and its resources are about to be unloaded.

When a non-empty string is assigned to the `returnValue` Event property, a dialog box appears, asking the users for confirmation to leave the page (see example below). When no value is provided, the event is processed silently. Some implementations only show the dialog box if the frame or any embedded frame receives a user gesture or user interaction. See [Browser compatibility](#browser_compatibility) for more information.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Target objects</td><td>defaultView</td></tr><tr class="even"><td>Interface</td><td><a href="event"><code>Event</code></a></td></tr></tbody></table>

## Examples

    window.addEventListener("beforeunload", function( event ) {
      event.returnValue = "\o/";
    });

    // is equivalent to
    window.addEventListener("beforeunload", function( event ) {
      event.preventDefault();
    });

WebKit-derived browsers don't follow the spec for the dialog box. An almost-cross-browser working example would be close to the below example.

    window.addEventListener("beforeunload", function (e) {
      var confirmationMessage = "\o/";

      (e || window.event).returnValue = confirmationMessage;     // Gecko + IE
      return confirmationMessage;                                /* Safari, Chrome, and other
                                                                  * WebKit-derived browsers */
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/browsing-the-web.html#the-beforeunloadevent-interface">HTML Living Standard<br />
<span class="small">The definition of 'BeforeUnloadEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`BeforeUnloadEvent`

30

12

1.5

Yes

17

Yes

≤37

30

4

18

Yes

3.0

`user_interaction`

60

≤79

?

?

47

?

60

60

?

44

?

8.0

## See also

- `DOMContentLoaded`
- `readystatechange`
- `load`
- `beforeunload`
- `unload`
- [Unloading Documents — Prompt to unload a document](https://www.whatwg.org/specs/web-apps/current-work/#prompt-to-unload-a-document)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BeforeUnloadEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BeforeUnloadEvent</a>
