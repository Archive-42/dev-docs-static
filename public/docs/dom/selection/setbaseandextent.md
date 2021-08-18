Selection.setBaseAndExtent()
============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `setBaseAndExtent()` method of the [`Selection`](../selection) interface sets the selection to be a range including all or parts of two specified DOM nodes, and any content located between them.

Syntax
------

    sel.setBaseAndExtent(anchorNode,anchorOffset,focusNode,focusOffset)

### Parameters

*`anchorNode`*  
The node at the start of the selection.

*`anchorOffset`*  
The number of child nodes from the start of the anchor node that should be excluded from the selection. So for example, if the value is 0 the whole node is included. If the value is 1, the whole node minus the first child node is included. And so on.

*`focusNode`*  
The node at the end of the selection.

`focusOffset`  
The number of child nodes from the start of the focus node that should be included in the selection. So for example, if the value is 0 the whole node is excluded. If the value is 1, the first child node is included. And so on.

**Note**: If the focus position appears before the anchor position in the document, the direction of the selection is reversed — the caret is placed at the beginning of the text rather the end, which matters for any keyboard command that might follow. For example, Shift + ➡︎ would cause the selection to narrow from the beginning rather than grow at the end.

### Return Value

Void.

### Exceptions

If `anchorOffset` is larger than the number of child nodes inside `anchorNode`, or if `focusOffset` is larger than the number of child nodes inside `focusNode`, an <span class="page-not-created">`IndexSizeError`</span> exception is thrown.

Examples
--------

In this example, we have two paragraphs containing spans, each one containing a single word. The first one is set as the `anchorNode` and the second is set as the `focusNode`. We also have an additional paragraph that sits in between the two nodes.

Next, we have two form inputs that allow you to set the `anchorOffset` and `focusOffset` — they both have a default value of 0.

We also have a button that when pressed invokes a function that runs the `setBaseAndExtent()` method with the specified offsets, and copies the selection into the output paragraph at the very bottom of the HTML.

    <h1>setBaseAndExtent example</h1>
    <div>
      <p class="one"><span>Fish</span><span>Dog</span><span>Cat</span><span>Bird</span></p>
      <p>MIDDLE</p>
      <p class="two"><span>Car</span><span>Bike</span><span>Boat</span><span>Plane</span></p>
    </div>

    <div>
      <p>
        <label for="aOffset">Anchor offset</label>
        <input id="aOffset" name="aOffset" type="number" value="0">
      </p>
      <p>
        <label for="fOffset">Focus offset</label>
        <input id="fOffset" name="fOffset" type="number" value="0">
      </p>
      <p><button>Capture selection</button></p>
    </div>

    <p><strong>Output</strong>: <span class="output"></span></p>

The JavaScript looks like so:

    var one = document.querySelector('.one');
    var two = document.querySelector('.two');

    var aOffset = document.getElementById('aOffset');
    var fOffset = document.getElementById('fOffset');

    var button = document.querySelector('button');

    var output = document.querySelector('.output');

    var selection;

    button.onclick = function() {
      try {
        selection = document.getSelection();
        selection.setBaseAndExtent(one, aOffset.value, two, fOffset.value);
        var text = selection.toString();
        output.textContent = text;
      } catch(e) {
        output.textContent = e.message;
      }
    }

Play with the live example below, setting different offset values to see how this affects the selection.

**Note**: You can find this [example on GitHub](https://github.com/chrisdavidmills/selection-api-examples/blob/master/setBaseAndExtent.html) ([see it live also](https://chrisdavidmills.github.io/selection-api-examples/setBaseAndExtent.html).)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-selection-setbaseandextent">Selection API<br />
<span class="small">The definition of 'Selection.setBaseAndExtent()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`setBaseAndExtent`

1

12

53

No

15

1.3

1

18

53

14

1

1.0

See also
--------

-   [`Selection`](../selection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection/setBaseAndExtent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection/setBaseAndExtent</a>
