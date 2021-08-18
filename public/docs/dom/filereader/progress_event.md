# FileReader: progress event

The `progress` event is fired periodically as the `FileReader` reads data.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../progressevent"><code>ProgressEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><span class="page-not-created"><code>FileReader.onprogress</code></span></td></tr></tbody></table>

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#dfn-progress-event">File API</a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`progress_event`

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

## See also

- Related events: [`loadstart`](loadstart_event), [`loadend`](loadend_event), [`load`](load_event), [`error`](error_event), [`abort`](abort_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileReader/progress_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileReader/progress_event</a>
