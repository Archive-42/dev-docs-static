# FileReader: loadstart event

The `loadstart` event is fired when a file read operation has begun.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../progressevent"><code>ProgressEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><span class="page-not-created"><code>FileReader.onloadstart</code></span></td></tr></tbody></table>

## Examples

### Live example

#### HTML

    <div class="example">

        <div class="file-select">
            <label for="avatar">Choose a profile picture:</label>
            <input type="file"
                   id="avatar" name="avatar"
                   accept="image/png, image/jpeg">
        </div>

        <img src="" class="preview" height="200" alt="Image preview...">

        <div class="event-log">
            <label>Event log:</label>
            <textarea readonly class="event-log-contents"></textarea>
        </div>

      </div>

#### JS

    const fileInput = document.querySelector('input[type="file"]');
    const preview = document.querySelector('img.preview');
    const eventLog = document.querySelector('.event-log-contents');
    const reader = new FileReader();

    function handleEvent(event) {
        eventLog.textContent = eventLog.textContent + `${event.type}: ${event.loaded} bytes transferred\n`;

        if (event.type === "load") {
            preview.src = reader.result;
        }
    }

    function addListeners(reader) {
        reader.addEventListener('loadstart', handleEvent);
        reader.addEventListener('load', handleEvent);
        reader.addEventListener('loadend', handleEvent);
        reader.addEventListener('progress', handleEvent);
        reader.addEventListener('error', handleEvent);
        reader.addEventListener('abort', handleEvent);
    }

    function handleSelected(e) {
        eventLog.textContent = '';
        const selectedFile = fileInput.files[0];
        if (selectedFile) {
            addListeners(reader);
            reader.readAsDataURL(selectedFile);
        }
    }

    fileInput.addEventListener('change', handleSelected);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#dfn-loadstart-event">File API</a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`loadstart_event`

Yes

12

79

Yes-79

`loadstart` event dispatches synchronously (should be asynchronously as per spec).

Yes

Yes

Yes

Yes

Yes

79

Yes-79

`loadstart` event dispatches synchronously (should be asynchronously as per spec).

Yes

Yes

Yes

## See also

- Related events: [`FileReader.load_event`](load_event), [`FileReader.loadend_event`](loadend_event), [`FileReader.progress_event`](progress_event), [`FileReader.error_event`](error_event), [`FileReader.abort_event`](abort_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileReader/loadstart_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileReader/loadstart_event</a>
