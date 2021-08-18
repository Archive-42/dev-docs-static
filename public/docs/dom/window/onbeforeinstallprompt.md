Window.onbeforeinstallprompt
============================

The `Window.onbeforeinstallprompt` property is an event handler for processing a `beforeinstallprompt`, which is dispatched on devices when a user is about to be prompted to "install" a web application. [Its associated event](../beforeinstallpromptevent) may be saved for later and used to prompt the user at a more suitable time.

Syntax
------

    window.addEventListener("beforeinstallprompt", function(event) { ... });
    window.onbeforeinstallprompt = function(event) { ...};

Example
-------

The following example uses the `beforeinstallprompt` event to make an install button operable, by using the event inside a click handler.

    window.addEventListener("beforeinstallprompt", function(beforeInstallPromptEvent) {
      beforeInstallPromptEvent.preventDefault(); // Prevents immediate prompt display

      // Shows prompt after a user clicks an "install" button
      installButton.addEventListener("click", function(mouseEvent) {
        // you should not use the MouseEvent here, obviously
        beforeInstallPromptEvent.prompt();
      });

      installButton.hidden = false; // Make button operable
    });

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

`onbeforeinstallprompt`

Yes

≤79

No

No

Yes

No

Yes

Yes

No

Yes

No

Yes

See also
--------

-   [`BeforeInstallPromptEvent.prompt`](../beforeinstallpromptevent/prompt)
-   [`BeforeInstallPromptEvent`](../beforeinstallpromptevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/onbeforeinstallprompt" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/onbeforeinstallprompt</a>
