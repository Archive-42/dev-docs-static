# BeforeInstallPromptEvent

The `BeforeInstallPromptEvent` is fired at the [`Window.onbeforeinstallprompt`](window/onbeforeinstallprompt) handler before a user is prompted to "install" a web site to a home screen on mobile.

This interface inherits from the [`Event`](event) interface.

## Constructor

<span class="page-not-created">`BeforeInstallPromptEvent()`</span>  
Creates a new `BeforeInstallPromptEvent`.

## Properties

_Inherits properties from its parent, [`Event`](event)._

<span class="page-not-created">`BeforeInstallPromptEvent.platforms`</span> <span class="badge inline readonly">Read only </span>  
Returns an array of [`DOMString`](domstring) items containing the platforms on which the event was dispatched. This is provided for user agents that want to present a choice of versions to the user such as, for example, "web" or "play" which would allow the user to chose between a web version or an Android version.

<span class="page-not-created">`BeforeInstallPromptEvent.userChoice`</span> <span class="badge inline readonly">Read only </span>  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`DOMString`](domstring) containing either "accepted" or "dismissed".

## Methods

[`BeforeInstallPromptEvent.prompt()`](beforeinstallpromptevent/prompt)  
Allows a developer to show the install prompt at a time of their own choosing. This method returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

## Example

    window.addEventListener("beforeinstallprompt", function(e) {
      // log the platforms provided as options in an install prompt
      console.log(e.platforms); // e.g., ["web", "android", "windows"]
      e.userChoice.then(function(choiceResult) {
        console.log(choiceResult.outcome); // either "accepted" or "dismissed"
      }, handleError);
    });

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

`BeforeInstallPromptEvent`

45

79

No

No

No

No

45

45

No

No

No

5.0

`BeforeInstallPromptEvent`

45

79

No

No

No

No

45

45

No

No

No

5.0

`platforms`

45

79

No

No

No

No

45

45

No

No

No

5.0

`prompt`

45

79

No

No

No

No

45

45

No

No

No

5.0

`userChoice`

45

79

No

No

No

No

45

45

No

No

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BeforeInstallPromptEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BeforeInstallPromptEvent</a>
