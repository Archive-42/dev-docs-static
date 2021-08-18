# NotifyAudioAvailableEvent

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The non-standard, obsolete, `NotifyAudioAvailableEvent` interface defines the event sent to audio elements when the audio buffer is full.

## Properties

`frameBuffer` <span class="badge inline readonly">Read only </span>  
A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) containing the raw 32-bit floating-point audio data obtained from decoding the audio (e.g., the raw data being sent to the audio hardware vs. encoded audio). The data is a series of audio samples, each sample containing one 32-bit value per audio channel. All audio frames are normalized to contain 1024 samples by default, but could be any length between 512 and 16384 samples if the user has set a different length using the `mozFrameBufferLength` attribute.

`time`  
A floating-point value indicating the time in seconds at which the first sample in the `frameBuffer` occurs, relative to the start of the audio track.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NotifyAudioAvailableEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NotifyAudioAvailableEvent</a>
