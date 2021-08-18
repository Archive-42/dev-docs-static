# BeforeInstallPromptEvent.prompt()

The `prompt()` method of the [`BeforeInstallPromptEvent`](../beforeinstallpromptevent) interface allows a developer to show the install prompt at a time of their own choosing.

## Syntax

    BeforeInstallPromptEvent.prompt()

### Parameters

None.

### Returns

An empty [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

## Example

    var isTooSoon = true;
    window.addEventListener("beforeinstallprompt", function(e) {
      if (isTooSoon) {
        e.preventDefault(); // Prevents prompt display
        // Prompt later instead:
        setTimeout(function() {
          isTooSoon = false;
          e.prompt(); // Throws if called more than once or default not prevented
        }, 10000);
      }

      // The event was re-dispatched in response to our request
      // ...
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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BeforeInstallPromptEvent/prompt" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BeforeInstallPromptEvent/prompt</a>
