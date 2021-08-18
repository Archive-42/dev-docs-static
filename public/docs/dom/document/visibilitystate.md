# Document.visibilityState

The `Document.visibilityState` read-only property returns the visibility of the [`document`](../document), that is in which context this element is now visible. It is useful to know if the document is in the background or an invisible tab, or only loaded for pre-rendering. Possible values are:

`visible`  
The page content may be at least partially visible. In practice this means that the page is the foreground tab of a non-minimized window.

`hidden`  
The page content is not visible to the user. In practice this means that the document is either a background tab or part of a minimized window, or the OS screen lock is active.

Safari doesn’t fire the `visibilitychange` event as expected when `visibilityState` transitions to `hidden`; so for that case, you need to also include code to listen for the `pagehide` event.

`prerender` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
The page content is being prerendered and is not visible to the user (considered hidden for purposes of `document.hidden`). The document may start in this state, but will never transition to it from another value. Note: This was removed from the standard. Check compatibility table for details.

When the value of this property changes, the [`visibilitychange`](visibilitychange_event) event is sent to the [`Document`](../document).

Typical use of this can be to prevent the download of some assets when the document is solely prerendered, or stop some activities when the document is in the background or minimized.

## Syntax

    var string = document.visibilityState

## Examples

    document.addEventListener("visibilitychange", function() {
      console.log( document.visibilityState );
      // Modify behavior...
    })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/page-visibility/#visibility-states-and-the-visibilitystate-enum">Page Visibility (Second Edition)<br />
<span class="small">The definition of 'Document.visibilityState' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`visibilityState`

33

13

12

18

10-52

10

20

15

12.1-15

6.1

4.4.3

≤37

33

18

18

10-52

20

14

12.1-14

7

2.0

1.0

`prerender`

Yes

≤79

49

?

?

6.1

Yes

Yes

49

?

7

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/visibilityState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/visibilityState</a>
