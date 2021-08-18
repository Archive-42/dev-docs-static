Selection.modify()
==================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `Selection.modify()` method applies a change to the current selection or cursor position, using simple textual commands.

Syntax
------

    sel.modify(alter, direction, granularity)

### Parameters

`alter`  
The type of change to apply. Specify `"move"` to move the current cursor position or `"extend"` to extend the current selection.

`direction`  
The direction in which to adjust the current selection. You can specify `"forward"` or `"backward"` to adjust in the appropriate direction based on the language at the selection point. If you want to adjust in a specific direction, you can specify `"left"` or `"right"`.

`granularity`  
The distance to adjust the current selection or cursor position. You can move by `"character"`, `"word"`, `"sentence"`, `"line"`, `"paragraph"`, `"lineboundary"`, `"sentenceboundary"`, `"paragraphboundary"`, or `"documentboundary"`.

**Note:** Gecko does **not** implement `"sentence"`, `"paragraph"`, `"sentenceboundary"`, `"paragraphboundary"`, or `"documentboundary"`. WebKit and Blink do.

**Note:** Starting in Gecko 5.0, the `"word"` granularity no longer includes the following space, regardless of the default platform behavior. This makes the behavior more consistent, as well as making it work the same way WebKit used to work, but unfortunately they have recently changed their behavior.

Example
-------

This example demonstrates the various `granularity` options for modifying a selection. Click somewhere inside the example (optionally selecting some text), and then click the button to expand the selection.

### HTML

    <p>Click somewhere in this example. Then click the button below to expand the selection. Watch what happens!</p>
    <p>Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil impedit quo minus id quod maxime placeat facere possimus, omnis voluptas assumenda est, omnis dolor repellendus.</p>

    <label for="granularity">Granularity:</label>
    <select id="granularity">
      <option value="character">Character</option>
      <option value="word">Word</option>
      <option value="sentence">Sentence</option>
      <option value="line">Line</option>
      <option value="paragraph">Paragraph</option>
      <option value="lineboundary">Line Boundary</option>
      <option value="sentenceboundary">Sentence Boundary</option>
      <option value="paragraphboundary">Paragraph Boundary</option>
      <option value="documentboundary">Document Boundary</option>
    </select>

    <br><br>

    <button>Extend selection</button>

### JavaScript

    let select = document.querySelector('select');
    let button = document.querySelector('button');

    button.addEventListener('click', modify);

    function modify() {
      let selection = window.getSelection();
      selection.modify('extend', 'forward', select.value);
    }

### Result

Specifications
--------------

*This method is not part of any specification.*

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

`modify`

1

≤79

4

No

15

1.3

1

18

4

14

1

1.0

`node`

Yes

≤79

55

No

Yes

Yes

Yes

Yes

55

Yes

Yes

Yes

`offset`

Yes

≤79

55

No

Yes

Yes

Yes

Yes

55

Yes

Yes

Yes

See also
--------

-   [`Selection`](../selection), the interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection/modify" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection/modify</a>
