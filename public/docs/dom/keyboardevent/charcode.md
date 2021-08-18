# KeyboardEvent.charCode

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `charCode` read-only property of the [`KeyboardEvent`](../keyboardevent) interface returns the Unicode value of a character key pressed during a `keypress` event.

**Do not use this property, as it is deprecated.** Instead, get the Unicode value of the character using the [`key`](key) property.

## Syntax

    var code = event.charCode;

### Return value

A number that represents the Unicode value of the character key that was pressed.

## Example

### HTML

    <p>Type anything into the input box below to log a <code>charCode</code>.</p>
    <input type="text" />
    <p id="log"></p>

### JavaScript

    let input = document.querySelector('input');
    let log = document.querySelector('#log');

    input.addEventListener('keypress', function(e) {
      log.innerText = `Key pressed: ${String.fromCharCode(e.charCode)}\ncharCode: ${e.charCode}`;
    });

### Result

## Notes

- In a `keypress` event, the Unicode value of the key pressed is stored in either the [`keyCode`](keycode) or `charCode` property, but never both. If the key pressed generates a character (e.g., 'a'), `charCode` is set to the code of that character; `charCode` respects the letter case (in other words, `charCode` takes into account whether the shift key is held down). Otherwise, the code of the pressed key is stored in `keyCode`.
- When one or more modifier keys are pressed, there are some complex rules for `charCode`. See [Gecko Keypress Event](https://developer.mozilla.org/en-US/docs/Gecko_Keypress_Event) for details.
- `charCode` is never set in the `keydown` and `keyup` events. In these cases, `keyCode` is set instead.
- To get the code of the key regardless of whether it was stored in `keyCode` or `charCode`, query the [`which`](which) property.
- Characters entered through an IME do not register through `keyCode` or `charCode`. <span class="comment">Actually with the Chinese IME I'm using, entering the IME results in a keypress event with keyCode = 229 and no other key events fire until the IME exits (which may happen after multiple characters are inputted). I'm not sure if other IME's work this way.</span>
- For a list of the `charCode` values associated with particular keys, run [Example 7: Displaying Event Object Properties](../document_object_model/examples#example_7:_displaying_event_object_properties) and view the resulting HTML table.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-KeyboardEvent-charCode">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'KeyboardEvent.charCode' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition; specified as deprecated</td></tr></tbody></table>

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

`charCode`

26

12

3

9

12.1

5.1

≤37

Yes

Yes

Yes

5.1

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/charCode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/charCode</a>
