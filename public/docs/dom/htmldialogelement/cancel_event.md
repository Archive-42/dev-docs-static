# HTMLDialogElement: cancel event

The `cancel` event fires on a [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog) when the user instructs the browser that they wish to dismiss the current open dialog. For example, the browser might fire this event when the user presses the Esc key or clicks a "Close dialog" button which is part of the browser's UI.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler</td><td><a href="../globaleventhandlers/oncancel"><code>oncancel</code></a></td></tr></tbody></table>

## Examples

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

    dialog.addEventListener('cancel', (event) => {
      result.textContent = 'dialog was canceled';
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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-cancel">HTML Living Standard<br />
<span class="small">The definition of 'cancel' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`cancel_event`

Yes

79

78

No

?

No

No

No

No

No

No

No

## See also

- [`GlobalEventHandlers.oncancel`](../globaleventhandlers/oncancel)
- HTML [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog) element
- [`close`](close_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement/cancel_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement/cancel_event</a>
