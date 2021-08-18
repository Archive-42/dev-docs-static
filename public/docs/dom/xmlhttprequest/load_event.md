XMLHttpRequest: load event
==========================

The `load` event is fired when an [`XMLHttpRequest`](../xmlhttprequest) transaction completes successfully.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../progressevent"><code>ProgressEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../xmlhttprequesteventtarget/onload"><code>onload</code></a></td></tr></tbody></table>

Examples
--------

### Live example

#### HTML

    <div class="controls">
        <input class="xhr success" type="button" name="xhr" value="Click to start XHR (success)" />
        <input class="xhr error" type="button" name="xhr" value="Click to start XHR (error)" />
        <input class="xhr abort" type="button" name="xhr" value="Click to start XHR (abort)" />
    </div>

    <textarea readonly class="event-log"></textarea>

#### JS

    const xhrButtonSuccess = document.querySelector('.xhr.success');
    const xhrButtonError = document.querySelector('.xhr.error');
    const xhrButtonAbort = document.querySelector('.xhr.abort');
    const log = document.querySelector('.event-log');

    function handleEvent(e) {
        log.textContent = log.textContent + `${e.type}: ${e.loaded} bytes transferred\n`;
    }

    function addListeners(xhr) {
        xhr.addEventListener('loadstart', handleEvent);
        xhr.addEventListener('load', handleEvent);
        xhr.addEventListener('loadend', handleEvent);
        xhr.addEventListener('progress', handleEvent);
        xhr.addEventListener('error', handleEvent);
        xhr.addEventListener('abort', handleEvent);
    }

    function runXHR(url) {
        log.textContent = '';

        const xhr = new XMLHttpRequest();
        addListeners(xhr);
        xhr.open("GET", url);
        xhr.send();
        return xhr;
    }

    xhrButtonSuccess.addEventListener('click', () => {
        runXHR('https://mdn.mozillademos.org/files/16553/DgsZYJNXcAIPwzy.jpg');
    });

    xhrButtonError.addEventListener('click', () => {
        runXHR('https://somewhere.org/i-dont-exist');
    });

    xhrButtonAbort.addEventListener('click', () => {
        runXHR('https://mdn.mozillademos.org/files/16553/DgsZYJNXcAIPwzy.jpg').abort();
    });

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#event-xhr-load">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`load_event`

Yes

≤79

Yes

9

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

See also
--------

-   Related events: [`loadstart`](loadstart_event), [`loadend`](loadend_event), [`progress`](progress_event), [`error`](error_event), [`abort`](abort_event)
-   [Monitoring progress](using_xmlhttprequest#monitoring_progress)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/load_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/load_event</a>
