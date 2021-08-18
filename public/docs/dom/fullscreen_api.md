# Fullscreen API

The **Fullscreen API** adds methods to present a specific [`Element`](element) (and its descendants) in full-screen mode, and to exit full-screen mode once it is no longer needed. This makes it possible to present desired content—such as an online game—using the user's entire screen, removing all browser user interface elements and other applications from the screen until full-screen mode is shut off.

See the article [Guide to the Fullscreen API](fullscreen_api/guide) for details on how to use the API.

**Note:** Support for this API varies somewhat across browsers, with many requiring vendor prefixes and/or not implementing the latest specification. See the [Browser compatibility](#browser_compatibility) section below for details on support for this API. You may wish to consider using a library such as [Fscreen](https://github.com/rafrex/fscreen) for vendor agnostic access to the Fullscreen API.

## Interfaces

_The Fullscreen API has no interfaces of its own. Instead, it augments several other interfaces to add the methods, properties, and event handlers needed to provide full-screen functionality. These are listed in the following sections._

## Methods

The Fullscreen API adds methods to the [`Document`](document) and [`Element`](element) interfaces to allow turning off and on full-screen mode.

### Methods on the Document interface

[`Document.exitFullscreen()`](document/exitfullscreen)  
Requests that the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) switch from full-screen mode back to windowed mode. Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is resolved once full-screen mode has been completely shut off.

### Methods on the Element interface

[`Element.requestFullscreen()`](element/requestfullscreen)  
Asks the user agent to place the specified element (and, by extension, its descendants) into full-screen mode, removing all of the browser's UI elements as well as all other applications from the screen. Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is resolved once full-screen mode has been activated.

## Properties

_The [`Document`](document) interface provides properties that can be used to determine if full-screen mode is supported and available, and if full-screen mode is currently active, which element is using the screen._

[`Document.fullscreenElement`](document/fullscreenelement) / [`ShadowRoot.fullscreenElement`](shadowroot/fullscreenelement)  
The `fullscreenElement` property tells you the [`Element`](element) that's currently being displayed in full-screen mode on the DOM (or shadow DOM). If this is `null`, the document (or shadow DOM) is not in full-screen mode.

[`document.fullscreenEnabled`](document/fullscreenenabled)  
The `fullscreenEnabled` property tells you whether or not it is possible to engage full-screen mode. This is `false` if full-screen mode is not available for any reason (such as the `"fullscreen"` feature not being allowed, or full-screen mode not being supported).

### Event handlers

_The Fullscreen API defines two events which can be used to detect when full-screen mode is turned on and off, as well as when errors occur during the process of changing between full-screen and windowed modes. Event handlers for these events are available on the [`Document`](document) and [`Element`](element) interfaces._

**Note:** These event handler properties are _not_ available as HTML content attributes. In other words, you cannot specify event handlers for `fullscreenchange` and `fullscreenerror` in the HTML content. They must be added by JavaScript code.

#### Event handlers on documents

[`Document.onfullscreenchange`](document/onfullscreenchange)  
An event handler for the `fullscreenchange` event that's bubbled up to the [`Document`](document) when any [`Element`](element) in that document is placed into full-screen mode, or exits full-screen mode.

[`Document.onfullscreenerror`](document/onfullscreenerror)  
An event handler for the `fullscreenerror` event that gets bubbled up to the [`Document`](document) when an error occurs while trying to enable or disable full-screen mode for any [`Element`](element) in that document.

#### Event handlers on elements

[`Element.onfullscreenchange`](element/onfullscreenchange)  
An event handler which is called when the `fullscreenchange` event is sent to the element, indicating that the element has been placed into, or removed from, full-screen mode.

[`Element.onfullscreenerror`](element/onfullscreenerror)  
An event handler for the `fullscreenerror` event when sent to an element which has encountered an error while transitioning into or out of full-screen mode.

### Obsolete properties

[`Document.fullscreen`](document/fullscreen) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A Boolean value which is `true` if the document has an element currently being displayed in full-screen mode; otherwise, this returns `false`.

**Note:** Use the [`fullscreenElement`](document/fullscreenelement) property on the [`Document`](document) or [`ShadowRoot`](shadowroot) instead; if it's not `null`, then it's an [`Element`](element) currently being displayed in full-screen mode.

## Events

_The Fullscreen API defines two events which can be used to detect when full-screen mode is turned on and off, as well as when errors occur during the process of changing between full-screen and windowed modes._

`fullscreenchange`  
Sent to an [`Element`](element) when it transitions into or out of full-screen mode.

`fullscreenerror`  
Sent to an `Element` if an error occurs while attempting to switch it into or out of full-screen mode.

## Dictionaries

[`FullscreenOptions`](fullscreenoptions)  
Provides optional settings you can specify when calling [`requestFullscreen()`](element/requestfullscreen).

## Controlling access

The availability of full-screen mode can be controlled using [Feature Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy). The full-screen mode feature is identified by the string `"fullscreen"`, with a default allow-list value of `"self"`, meaning that full-screen mode is permitted in top-level document contexts, as well as to nested browsing contexts loaded from the same origin as the top-most document.

See [Using Feature Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy/Using_Feature_Policy) to learn more about using Feature Policy to control access to an API.

## Usage notes

Users can choose to exit full-screen mode by pressing the ESC (or F11) key, rather than waiting for the site or app to programmatically do so. Make sure you provide, somewhere in your user interface, appropriate user interface elements that inform the user that this option is available to them.

**Note:** Navigating to another page, changing tabs, or switching to another application using any application switcher (or Alt-Tab) will likewise exit full-screen mode.

## Examples

### Simple fullscreen usage

In this example, a video is presented in a web page. Pressing the Enter key lets the user toggle between windowed and full-screen presentation of the video.

[View Live Example](https://mdn.github.io/dom-examples/fullscreen-api/index.html)

#### Watching for the Enter key

When the page is loaded, this code is run to set up an event listener to watch for the Enter key.

    document.addEventListener("keypress", function(e) {
      if (e.keyCode === 13) {
        toggleFullScreen();
      }
    }, false);

#### Toggling full-screen mode

This code is called by the event handler above when the user hits the Enter key.

    function toggleFullScreen() {
      if (!document.fullscreenElement) {
          document.documentElement.requestFullscreen();
      } else {
        if (document.exitFullscreen) {
          document.exitFullscreen();
        }
      }
    }

This starts by looking at the value of the [`document`](document)'s `fullscreenElement` attribute. In a real-world deployment, at this time, you'll want to check for prefixed versions of this (`mozFullScreenElement`, `msFullscreenElement`, or `webkitFullscreenElement`, for example). If the value is `null`, the document is currently in windowed mode, so we need to switch to full-screen mode; otherwise, it's the element that's currently in full-screen mode. Switching to full-screen mode is done by calling [`Element.requestFullscreen()`](element/requestfullscreen) on the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element.

If full-screen mode is already active (`fullscreenElement` is not `null`), we call [`exitFullscreen()`](document/exitfullscreen) on the `document` to shut off full-screen mode.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://fullscreen.spec.whatwg.org/">Fullscreen API</a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`Fullscreen_API`

71

15

79

79

12-14

64

9

Before Firefox 44, Firefox incorrectly allowed elements inside a `<frame>` or `<object>` element to request, and to be granted, fullscreen. In Firefox 44 and onwards this has been fixed: only elements in the top-level document or in an `<iframe>` element with the `allowfullscreen` attribute can be displayed fullscreen.

11

58

15

12-15

6

71

≤37

71

18

64

9

Before Firefox 44, Firefox incorrectly allowed elements inside a `<frame>` or an `<object>` to request, and to be granted, fullscreen. In Firefox 44 and onwards this has been fixed: only elements in the top-level document or in an `<iframe>` with the `allowfullscreen` attribute can be displayed fullscreen.

50

14

12-14

6

Only available on iPad, not on iPhone. Shows an overlay button which can not be disabled.

10.0

1.0

`options_parameter`

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

`returns_a_promise`

69

79

64

No

No

No

69

69

64

No

No

10.0

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

`Fullscreen_API`

71

15

12

64

9

11

15

5.1

71

≤37

71

18

64

9

Yes

No

10.0

1.0

`returns_a_promise`

69

79

64

No

?

?

69

69

64

?

No

10.0

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

`Fullscreen_API`

71

Yes

12

64

10

11

Yes

6

71

Yes

71

Yes

64

10

Yes

6

10.0

Yes

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

`Fullscreen_API`

71

53

≤79

≤18

12

64

9

Yes

58

40

Yes

71

53

71

53

64

9

50

41

12

Full-screen mode is only supported on the iPad.

10.0

6.0

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

`Fullscreen_API`

71

15

79

≤79

64

9

No

58

15

6

71

≤37

71

18

64

9

50

14

6

10.0

1.0

BCD tables only load in the browser

### Document.fullscreenElement

BCD tables only load in the browser

### Document.fullscreenEnabled

BCD tables only load in the browser

### Document.exitFullscreen

BCD tables only load in the browser

### Element.requestFullscreen

BCD tables only load in the browser

## See also

- [Using full-screen mode](fullscreen_api)
- [`Element.requestFullscreen()`](element/requestfullscreen)
- [`Document.exitFullscreen()`](document/exitfullscreen)
- [`Document.fullscreen`](document/fullscreen)
- [`Document.fullscreenElement`](document/fullscreenelement)
- [`:fullscreen`](https://developer.mozilla.org/en-US/docs/Web/CSS/:fullscreen), [`::backdrop`](https://developer.mozilla.org/en-US/docs/Web/CSS/::backdrop)
- [`allowfullscreen`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-allowfullscreen)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API</a>
