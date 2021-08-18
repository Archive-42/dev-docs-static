FileReader: error event
=======================

The `error` event is fired when the read failed due to an error (for example, because the file was not found or not readable).

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../progressevent"><code>ProgressEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onerror"><code>FileReader.onerror</code></a></td></tr></tbody></table>

Examples
--------

    const fileInput = document.querySelector('input[type="file"]');
    const reader = new FileReader();

    function handleSelected(e) {
        const selectedFile = fileInput.files[0];
        if (selectedFile) {

            reader.addEventListener('error', () => {
                console.error(`Error occurred reading file: ${selectedFile.name}`);
            });

            reader.addEventListener('load', () => {
                console.error(`File: ${selectedFile.name} read successfully`);
            });

            reader.readAsDataURL(selectedFile);
        }
    }

    fileInput.addEventListener('change', handleSelected);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#dfn-error-event">File API</a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`error_event`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   Related events: [`loadstart`](loadstart_event), [`loadend`](loadend_event), [`progress`](progress_event), [`load`](load_event), [`abort`](abort_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileReader/error_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileReader/error_event</a>
