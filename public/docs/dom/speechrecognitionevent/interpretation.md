SpeechRecognitionEvent.interpretation
=====================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `interpretation` read-only property of the [`SpeechRecognitionEvent`](../speechrecognitionevent) interface returns the semantic meaning of what the user said.

This might be determined, for instance, through the SISR specification of semantics in a grammar (see [Semantic Interpretation for Speech Recognition (SISR) Version 1.0](https://www.w3.org/TR/semantic-interpretation/) for specification and examples.)

Syntax
------

    var myInterpretation = event.interpretation;

### Value

The returned value can be of any type. If no semantic interpretation has been returned by the speec recognition system, `null` will be returned.

Examples
--------

    recognition.onresult = function(event) {
      var color = event.results[0][0].transcript;
      diagnostic.textContent = 'Result received: ' + color + '.';
      bg.style.backgroundColor = color;
      console.log(event.interpretation);
    }

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

`interpretation`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

No

≤37

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionEvent/interpretation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionEvent/interpretation</a>
