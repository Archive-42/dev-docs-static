# FullscreenOptions.navigationUI

The [`FullscreenOptions`](../fullscreenoptions) dictionary's `navigationUI` property is used when calling [`requestFullscreen()`](../element/requestfullscreen) to specify to what extent the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) should include its standard user interface while the element is presented in full-screen mode.

## Syntax

    let fullscreenOptions = {
      navigationUI: value
    };

### Value

The value of the `navigationUI` property must be one of the following strings. The default is `"auto"`.

`"hide"`  
The browser's navigation interface will be hidden and the entire dimensions of the screen will be allocated to the display of the element.

`"show"`  
The browser will present page navigation controls and possibly other user interface; the dimensions of the element (and the perceived size of the screen) will be clamped to leave room for this user interface.

`"auto"`  
The browser will choose which of the above settings to apply. This is the default value.

## Example

In this example, the entire document is placed into full-screen mode by calling [`requestFullscreen()`](../element/requestfullscreen) on the document's [`Document.documentElement`](../document/documentelement), which is the document's root [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) element.

    let elem = document.documentElement;

    elem.requestFullscreen({ navigationUI: "show" }).then({}).catch(err => {
      alert(`An error occurred while trying to switch into full-screen mode: ${err.message} (${err.name})`);
    });

The promise's resolve handler does nothing, but if the promise is rejected, an error message is displayed by calling [`alert()`](../window/alert).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fullscreen.spec.whatwg.org/#dictdef-fullscreenoptions">Fullscreen API<br />
<span class="small">The definition of 'FullscreenOptions' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`navigationUI`

71

79

64

No

?

?

71

71

64

?

?

10.0

## See also

- [Fullscreen API](../fullscreen_api)
- [Guide to the Fullscreen API](../fullscreen_api/guide)
- [`Element.requestFullscreen()`](../element/requestfullscreen)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FullscreenOptions/navigationUI" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FullscreenOptions/navigationUI</a>
