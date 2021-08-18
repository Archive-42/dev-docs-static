# Document: readystatechange event

The `readystatechange` event is fired when the [`readyState`](readystate) attribute of a document has changed.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onreadystatechange</code></td></tr></tbody></table>

## Examples

### Live example

#### HTML

    <div class="controls">
      <button id="reload" type="button">Reload</button>
    </div>

    <div class="event-log">
      <label>Event log:</label>
      <textarea readonly class="event-log-contents" rows="8" cols="30"></textarea>
    </div>

#### JS

    const log = document.querySelector('.event-log-contents');
    const reload = document.querySelector('#reload');

    reload.addEventListener('click', () => {
      log.textContent ='';
      window.setTimeout(() => {
          window.location.reload(true);
      }, 200);
    });

    window.addEventListener('load', (event) => {
        log.textContent = log.textContent + 'load\n';
    });

    document.addEventListener('readystatechange', (event) => {
        log.textContent = log.textContent + `readystate: ${document.readyState}\n`;
    });

    document.addEventListener('DOMContentLoaded', (event) => {
        log.textContent = log.textContent + `DOMContentLoaded\n`;
    });

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-readystatechange">HTML Living Standard<br />
<span class="small">The definition of 'readystatechange' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`readystatechange_event`

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

- Related events: `DOMContentLoaded`, `load`, `beforeunload`, `unload`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/readystatechange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/readystatechange_event</a>
