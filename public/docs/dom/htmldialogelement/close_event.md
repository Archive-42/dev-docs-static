HTMLDialogElement: close event
==============================

The `close` event is fired on an `HTMLDialogElement` object when the dialog it represents has been closed.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onclose</code></td></tr></tbody></table>

Examples
--------

### Live example

#### HTML

    <dialog class="example-dialog">
        <button class="close" type="reset">Close</button>
    </dialog>

    <button class="open-dialog">Open dialog</button>

    <div class="result"></div>

#### JS

    const result = document.querySelector('.result');

    const dialog = document.querySelector('.example-dialog');
    dialog.addEventListener('close', (event) => {
        result.textContent = 'dialog was closed';
    });

    const openDialog = document.querySelector('.open-dialog');
    openDialog.addEventListener('click', () => {
      if (typeof dialog.showModal === 'function') {
          dialog.showModal();
          result.textContent = '';
      } else {
          result.textContent = 'The dialog API is not supported by this browser';
      }
    });

    const closeButton = document.querySelector('.close');
    closeButton.addEventListener('click', () => {
        dialog.close();
    });

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-close">HTML Living Standard<br />
<span class="small">The definition of 'close' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`close_event`

Yes

79

No

No

?

No

No

No

No

No

No

No

See also
--------

-   HTML `<dialog>` element

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement/close_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement/close_event</a>
