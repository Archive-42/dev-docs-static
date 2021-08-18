# KeyboardEvent.metaKey

The `KeyboardEvent.metaKey` read-only property returning a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates if the Meta key was pressed (`true`) or not (`false`) when the event occurred. Some operating systems may intercept the key so it is never detected.

**Note:** On Macintosh keyboards, this is the ⌘ Command key.

At least as of Firefox 48, the ⊞ Windows key is no longer considered the "Meta" key. `KeyboardEvent.metaKey` is `false` when the ⊞ Windows key is pressed.

## Syntax

    var metaKeyPressed = instanceOfKeyboardEvent.metaKey

### Return value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)

## Example

    function ismetaKey(e) {
      alert("metaKey = " + e.metaKey);
    }

    <button onclick="ismetaKey(event)">Click me with the meta key</button>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-KeyboardEvent-metaKey">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'KeyboardEvent.metaKey' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`metaKey`

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

- [`KeyboardEvent`](../keyboardevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/metaKey" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/metaKey</a>
