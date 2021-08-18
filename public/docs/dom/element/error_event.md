# Element: error event

The `error` event is fired on an [`Element`](../element) object when a resource failed to load, or can't be used. For example, if a script has an execution error or an image can't be found or is invalid.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a> or <a href="../uievent"><code>UIEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onerror"><code>onerror</code></a></td></tr></tbody></table>

The event object is a [`UIEvent`](../uievent) instance if it was generated from a user interface element, or an [`Event`](../event) instance otherwise.

## Examples

### Live example

#### HTML

    <div class="controls">
      <button id="img-error" type="button">Generate image error</button>
      <img class="bad-img" />
    </div>

    <div class="event-log">
      <label>Event log:</label>
      <textarea readonly class="event-log-contents" rows="8" cols="30"></textarea>
    </div>

#### JS

    const log = document.querySelector('.event-log-contents');

    const badImg = document.querySelector('.bad-img');
    badImg.addEventListener('error', (event) => {
        log.textContent = log.textContent + `${event.type}: Loading image\n`;
        console.log(event)
    });

    const imgError = document.querySelector('#img-error');
    imgError.addEventListener('click', () => {
        badImg.setAttribute('src', 'i-dont-exist');
    });

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-error">UI Events</a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`error_event`

Yes

≤79

Yes

?

?

?

Yes

Yes

Yes

?

?

Yes

## See also

- This event on `Window` targets: [`error`](../window/error_event) event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/error_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/error_event</a>
