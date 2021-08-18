# HTMLAudioElement.msAudioDeviceType

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `msAudioDeviceType` property of the HTML [&lt;audio&gt;](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) element, is a read/write proprietary attribute, specific to Internet Explorer and Microsoft Edge.

`msAudioDeviceType` specifies the output device id that the audio will be sent to.

## Syntax

    <audio src="sound.mp3" msAudioDeviceType="Communications" />

By default, audio on your system will output to your default speakers and be considered a foreground element, meaning that the audio will play only when the element is active in the app. For real-time communications, you can use the `msAudioDeviceType` property with the value `Console`, `Multimedia`, or `Communications` to specify where the current audio should output.

## Value

Include a description of the property's value, including data type and what it represents.

<table><thead><tr class="header"><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td>Console</td><td>Specifies that the audio output will be sent to the console device.</td></tr><tr class="even"><td>Multimedia</td><td>Specifies that the audio output will be sent to the multimedia device.</td></tr><tr class="odd"><td>Communications</td><td>Specifies that the audio output will be sent to the communications device.</td></tr></tbody></table>

## See also

- [Microsoft API extensions](../microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAudioElement/msAudioDeviceType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAudioElement/msAudioDeviceType</a>
