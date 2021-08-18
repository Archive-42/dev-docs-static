Selection
=========

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

A `Selection` object represents the range of text selected by the user or the current position of the caret. To obtain a `Selection` object for examination or manipulation, call [`window.getSelection()`](window/getselection).

A user may make a selection from left to right (in document order) or right to left (reverse of document order). The **anchor** is where the user began the selection and the **focus** is where the user ends the selection. If you make a selection with a desktop mouse, the anchor is placed where you pressed the mouse button, and the focus is placed where you released the mouse button.

*Anchor* and *focus* should not be confused with the *start* and *end* positions of a selection. The anchor can be placed before the focus or vice-versa, depending on the direction you made your selection.

Properties
----------

 [`Selection.anchorNode`](selection/anchornode)<span class="badge inline readonly">Read only </span>   
Returns the [`Node`](node) in which the selection begins. Can return `null` if selection never existed in the document (e.g., an iframe that was never clicked on).

 [`Selection.anchorOffset`](selection/anchoroffset)<span class="badge inline readonly">Read only </span>   
Returns a number representing the offset of the selection's anchor within the `anchorNode`. If `anchorNode` is a text node, this is the number of characters within anchorNode preceding the anchor. If `anchorNode` is an element, this is the number of child nodes of the `anchorNode` preceding the anchor.

 [`Selection.focusNode`](selection/focusnode)<span class="badge inline readonly">Read only </span>   
Returns the [`Node`](node) in which the selection ends. Can return `null` if selection never existed in the document (for example, in an `iframe` that was never clicked on).

 [`Selection.focusOffset`](selection/focusoffset)<span class="badge inline readonly">Read only </span>   
Returns a number representing the offset of the selection's anchor within the `focusNode`. If `focusNode` is a text node, this is the number of characters within `focusNode` preceding the focus. If `focusNode` is an element, this is the number of child nodes of the `focusNode` preceding the focus.

 [`Selection.isCollapsed`](selection/iscollapsed)<span class="badge inline readonly">Read only </span>   
Returns a Boolean indicating whether the selection's start and end points are at the same position.

 [`Selection.rangeCount`](selection/rangecount)<span class="badge inline readonly">Read only </span>   
Returns the number of ranges in the selection.

 [`Selection.type`](selection/type)<span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) describing the type of the current selection.

Methods
-------

[`Selection.addRange()`](selection/addrange)  
A [`Range`](range) object that will be added to the selection.

[`Selection.collapse()`](selection/collapse)  
Collapses the current selection to a single point.

[`Selection.collapseToEnd()`](selection/collapsetoend)  
Collapses the selection to the end of the last range in the selection.

[`Selection.collapseToStart()`](selection/collapsetostart)  
Collapses the selection to the start of the first range in the selection.

[`Selection.containsNode()`](selection/containsnode)  
Indicates if a certain node is part of the selection.

[`Selection.deleteFromDocument()`](selection/deletefromdocument)  
Deletes the selection's content from the document.

[`Selection.empty()`](selection/removeallranges)  
Removes all ranges from the selection. This is an alias for `removeAllRanges()` — See [`Selection.removeAllRanges()`](selection/removeallranges) for more details.

[`Selection.extend()`](selection/extend)  
Moves the focus of the selection to a specified point.

[`Selection.getRangeAt()`](selection/getrangeat)  
Returns a [`Range`](range) object representing one of the ranges currently selected.

 [`Selection.modify()`](selection/modify)<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Changes the current selection.

[`Selection.removeRange()`](selection/removerange)  
Removes a range from the selection.

[`Selection.removeAllRanges()`](selection/removeallranges)  
Removes all ranges from the selection.

[`Selection.selectAllChildren()`](selection/selectallchildren)  
Adds all the children of the specified node to the selection.

[`Selection.setBaseAndExtent()`](selection/setbaseandextent)  
Sets the selection to be a range including all or parts of two specified DOM nodes, and any content located between them.

[`Selection.setPosition()`](selection/collapse)  
Collapses the current selection to a single point. This is an alias for `collapse()` — See [`Selection.collapse()`](selection/collapse) for more details.

[`Selection.toString()`](selection/tostring)  
Returns a string currently being represented by the selection object, i.e. the currently selected text.

Notes
-----

### String representation of a selection

Calling the [`Selection.toString()`](selection/tostring) method returns the text contained within the selection, e.g.:

    var selObj = window.getSelection();
    window.alert(selObj);

Note that using a selection object as the argument to `window.alert` will call the object's `toString` method.

### Multiple ranges in a selection

A selection object represents the [`Range`](range)s that the user has selected. Typically, it holds only one range, accessed as follows:

    var selObj = window.getSelection();
    var range  = selObj.getRangeAt(0);

-   `selObj` is a Selection object
-   `range` is a [`Range`](range) object

As the [Selection API specification notes](https://www.w3.org/TR/selection-api/#h_note_15), the Selection API was initially created by Netscape and allowed multiple ranges (for instance, to allow the user to select a column from a [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)). However, browsers other than Gecko did not implement multiple ranges, and the specification also requires the selection to always have a single range.

### Selection and input focus

Selection and input focus (indicated by [`Document.activeElement`](document/activeelement)) have a complex relationship that varies by browser. In cross-browser compatible code, it's better to handle them separately.

Safari and Chrome (unlike Firefox) currently focus the element containing selection when modifying the selection programmatically; it's possible that this may change in the future (see [W3C bug 14383](https://www.w3.org/Bugs/Public/show_bug.cgi?id=14383) and [WebKit bug 38696](https://bugs.webkit.org/show_bug.cgi?id=38696)).

### Behavior of Selection API in terms of editing host focus changes

The Selection API has a common behavior (i.e., shared between browsers) that governs how focus behavior changes for editing hosts after certain methods are called.

The behavior is as follows:

1.  An editing host gains focus if the previous selection was outside of it.
2.  A Selection API method is called, causing a new selection to be made with the selection range inside the editing host.
3.  Focus then moves to the editing host.

**Note**: The Selection API methods may only move focus to an editing host, not to other focusable elements (e.g., [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)).

The above behavior applies to selections made using the following methods:

-   [`Selection.collapse()`](selection/collapse)
-   [`Selection.collapseToStart()`](selection/collapsetostart)
-   [`Selection.collapseToEnd()`](selection/collapsetoend)
-   [`Selection.extend()`](selection/extend)
-   [`Selection.selectAllChildren()`](selection/selectallchildren)
-   [`Selection.addRange()`](selection/addrange)
-   [`Selection.setBaseAndExtent()`](selection/setbaseandextent)

And when the [`Range`](range) is modified using the following methods:

-   [`Range.setStart()`](range/setstart)
-   [`Range.setEnd()`](range/setend)
-   [`Range.setStartBefore()`](range/setstartbefore)
-   [`Range.setStartAfter()`](range/setstartafter)
-   [`Range.setEndBefore()`](range/setendbefore)
-   [`Range.setEndAfter()`](range/setendafter)
-   [`Range.collapse()`](range/collapse)
-   [`Range.selectNode()`](range/selectnode)
-   [`Range.selectNodeContents()`](range/selectnodecontents)

### Glossary

Other key terms used in this section.

anchor  
The anchor of a selection is the beginning point of the selection. When making a selection with a mouse, the anchor is where in the document the mouse button is initially pressed. As the user changes the selection using the mouse or the keyboard, the anchor does not move.

editing host  
An editable element (e.g., an HTML element with [`contenteditable`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-contenteditable) set, or the HTML child of a document that has [`designMode`](document/designmode) enabled).

focus of a selection  
The focus of a selection is the end point of the selection. When making a selection with a mouse, the focus is where in the document the mouse button is released. As the user changes the selection using the mouse or the keyboard, the focus is the end of the selection that moves.

This is not the same as the focused *element* of the document, as returned by [`document.activeElement`](document/activeelement).

range  
A range is a contiguous part of a document. A range can contain entire nodes as well as portions of nodes (such as a portion of a text node). A user will normally only select a single range at a time, but it's possible for a user to select multiple ranges (e.g., by using the Control key). A range can be retrieved from a selection as a [`range`](range) object. Range objects can also be created via the DOM and programmatically added or removed from a selection.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#selection-interface">Selection API<br />
<span class="small">The definition of 'Selection' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>The Selection API specification is based on the HTML Editing APIs specification and focuses on the Selection-related functionality.</td></tr></tbody></table>

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

`Selection`

1

12

1

The [`GlobalEventHandlers.onselectionchange`](https://developer.mozilla.org/docs/Web/API/GlobalEventHandlers/onselectionchange) and [`GlobalEventHandlers.onselectstart`](https://developer.mozilla.org/docs/Web/API/GlobalEventHandlers/onselectstart) event handlers are supported as of Firefox 52.

9

9

1

1

18

4

The [`GlobalEventHandlers.onselectionchange`](https://developer.mozilla.org/docs/Web/API/GlobalEventHandlers/onselectionchange) and [`GlobalEventHandlers.onselectstart`](https://developer.mozilla.org/docs/Web/API/GlobalEventHandlers/onselectstart) event handlers are supported as of Firefox 52.

10.1

1

1.0

`addRange`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`anchorNode`

1

12

1

9

≤12.1

1.3

1

18

4

≤12.1

1

1.0

`anchorOffset`

1

12

1

9

≤12.1

1.3

1

18

4

≤12.1

1

1.0

`collapse`

1

12

1

9

≤12.1

1.3

1

18

4

≤12.1

1

1.0

`collapseToEnd`

1

12

1

9

≤12.1

1.3

1

18

4

≤12.1

1

1.0

`collapseToStart`

1

12

1

9

≤12.1

1.3

1

18

4

≤12.1

1

1.0

`containsNode`

1

12

1

Before Firefox 35, the method didn't throw if `node` was `null`.

No

≤12.1

3.1

1

18

4

Before Firefox 35, the method didn't throw if `node` was `null`.

≤12.1

2

1.0

`deleteFromDocument`

1

12

1

9

≤12.1

3.1

1

18

4

≤12.1

2

1.0

`empty`

1

12

55

No

15

1.3

1

18

55

14

1

1.0

`extend`

1

12

1

No

≤12.1

3.1

1

18

4

≤12.1

2

1.0

`focusNode`

1

12

1

9

≤12.1

5.1

1

18

4

≤12.1

Yes

1.0

`focusOffset`

1

12

1

9

≤12.1

1.3

1

18

4

≤12.1

1

1.0

`getRangeAt`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`isCollapsed`

1

12

1

9

≤12.1

1.3

1

18

4

≤12.1

1

1.0

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

`rangeCount`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`removeAllRanges`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`removeRange`

58

12

1

9

45

≤12.1-15

No

58

58

4

43

≤12.1-14

No

7.0

`selectAllChildren`

1

12

1

9

≤12.1

3.1

1

18

4

≤12.1

2

1.0

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

`setPosition`

1

14

55

No

15

1.3

1

18

55

14

1

1.0

`toString`

1

≤18

1

9

≤12.1

Yes

1

18

4

≤12.1

Yes

1.0

`type`

1

12

57

No

15

1.3

1

18

57

14

1

1.0

### Gecko notes

-   Gecko/Firefox provide additional features, available to chrome (internal and add-on) code only. These are defined in <span class="page-not-created">`nsISelectionPrivate`</span>.
-   Mozilla source code: `dom/webidl/Selection.webidl`
-   [`Selection.selectionLanguageChange()`](selection/selectionlanguagechange)<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> used to be exposed to the web content until Firefox 29

See also
--------

-   [`Window.getSelection`](window/getselection), [`Document.getSelection`](document/getselection), [`Range`](range)
-   Selection-related events: `selectionchange` and `selectstart`
-   HTML inputs provide simpler helper APIs for working with selection (see [`HTMLInputElement.setSelectionRange()`](htmlinputelement/setselectionrange))
-   [`Document.activeElement`](document/activeelement), [`HTMLElement.focus()`](htmlorforeignelement/focus), and [`HTMLElement.blur()`](htmlorforeignelement/blur)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection</a>
