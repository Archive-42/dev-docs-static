SpeechRecognitionEvent.resultIndex
==================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `resultIndex` read-only property of the [`SpeechRecognitionEvent`](../speechrecognitionevent) interface returns the lowest index value result in the [`SpeechRecognitionResultList`](../speechrecognitionresultlist) "array" that has actually changed.

The [`SpeechRecognitionResultList`](../speechrecognitionresultlist) object is not an array, but it has a getter that allows it to be accessed by array syntax.

Syntax
------

    var myResultIndex = event.resultIndex;

### Value

A number.

Examples
--------

    recognition.onresult = function(event) {
      var color = event.results[0][0].transcript;
      diagnostic.textContent = 'Result received: ' + color + '.';
      bg.style.backgroundColor = color;
      console.log(event.resultIndex); // returns 0 if there is only one result
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechrecognitionevent-resultindex">Web Speech API<br />
<span class="small">The definition of 'resultIndex' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`resultIndex`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

≤37

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionEvent/resultIndex" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionEvent/resultIndex</a>
