SpeechRecognition.serviceURI
============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `serviceURI` property of the [`SpeechRecognition`](../speechrecognition) interface specifies the location of the speech recognition service used by the current `SpeechRecognition` to handle the actual recognition. The default is the user agent's default speech service.

Syntax
------

    var myServiceURI = mySpeechRecognition.serviceURI;
    mySpeechRecognition.serviceURI = 'path/to/my/service/';

### Value

A [`DOMString`](../domstring) representing the URI of the speech recognition service.

Examples
--------

    var recognition = new SpeechRecognition();

    recognition.serviceURI = 'http://www.example.com';

    ...

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

`serviceURI`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

No

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

No

Yes

You'll need to serve your code through a web server for recognition to work.

### Firefox OS permissions

To use speech recognition in an app, you need to specify the following permissions in your [manifest](https://developer.mozilla.org/en-US/docs/Web/Apps/Build/Manifest):

    "permissions": {
      "audio-capture" : {
        "description" : "Audio capture"
      },
      "speech-recognition" : {
        "description" : "Speech recognition"
      }
    }

You also need a privileged app, so you need to include this as well:

      "type": "privileged"

See also
--------

-   [Web Speech API](../web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition/serviceURI" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition/serviceURI</a>
