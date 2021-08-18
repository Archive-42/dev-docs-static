HTML attribute: capture
=======================

**Draft**

This page is not complete.

<span class="summary">The `capture` attribute specifies that, optionally, a new file should be captured, and which device should be used to capture that new media of a type defined by the `accept` attribute. </span>Values include `user` and `environment`. The capture attribute is supported on the [file](../element/input/file) input type.

The `capture` attribute takes as it's value a string that specifies which camera to use for capture of image or video data, if the [accept](accept) attribute indicates that the input should be of one of those types.

<table><thead><tr class="header"><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>user</code></td><td>The user-facing camera and/or microphone should be used.</td></tr><tr class="even"><td><code>environment</code></td><td>The outward-facing camera and/or microphone should be used</td></tr></tbody></table>

Note: capture was previously a Boolean attribute which, if present, requested that the device's media capture device(s) such as camera or microphone be used instead of requesting a file input.

Examples
--------

When set on a file input type, operating systems with microphones and cameras will display a user interface allowing the selection from an existing file or the creating of a new one.

    <p>
        <label for="soundFile">What does your voice sound like?:</label>
        <input type="file" id="soundFile" capture="user" accept="audio/*">
        </p>
        <p>
        <label for="videoFile">Upload a video:</label>
        <input type="file" id="videoFile" capture="environment" accept="video/*">
        </p>
        <p>
        <label for="imageFile">Upload a photo of yourself:</label>
        <input type="file" id="imageFile" capture="user" accept="image/*">
        </p>

Note these work better on mobile devices; if your device is a desktop computer, you'll likely get a typical file picker.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/html-media-capture/#the-capture-attribute">HTML Media Capture<br />
<span class="small">The definition of 'capture attribute' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `html.elements.attribute.capture`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [Using files from web applications](https://developer.mozilla.org/en-US/docs/Web/API/File/Using_files_from_web_applications)
-   [File API](https://developer.mozilla.org/en-US/docs/Web/API/File)
-   <span class="page-not-created">`HTMLInputElement.files`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/capture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/capture</a>
