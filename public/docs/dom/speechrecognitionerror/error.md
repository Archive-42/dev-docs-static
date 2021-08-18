SpeechRecognitionError.error
============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `error` read-only property of the [`SpeechRecognitionError`](../speechrecognitionerror) interface returns the type of error raised.

This `SpeechRecognitionError` interface was renamed to [`SpeechRecognitionErrorEvent`](../speechrecognitionerrorevent) in the Web Speech API specification.

Syntax
------

    var myError = event.error;

### Value

A [`DOMString`](../domstring) naming the type of error. The possible error types are:

no-speech  
No speech was detected.

aborted  
Speech input was aborted in some manner, perhaps by some user-agent-specific behavior like a button the user can press to cancel speech input.

audio-capture  
Audio capture failed.

network  
Network communication required for completing the recognition failed.

not-allowed  
The user agent disallowed any speech input from occurring for reasons of security, privacy or user preference.

service-not-allowed  
The user agent disallowed the requested speech recognition service, either because the user agent doesn't support it or because of reasons of security, privacy or user preference. In this case it would allow another more suitable speech recognition service to be used instead.

bad-grammar  
There was an error in the speech recognition grammar or semantic tags, or the chosen grammar format or semantic tag format was unsupported.

language-not-supported  
The language was not supported.

Examples
--------

    var recognition = new SpeechRecognition();

    recognition.onerror = function(event) {
      console.log('Speech recognition error detected: ' + event.error);
      console.log('Additional information: ' + event.message);
    }

Browser compatibility
---------------------

No compatibility data found for `api.SpeechRecognitionError.error`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionError/error" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionError/error</a>
