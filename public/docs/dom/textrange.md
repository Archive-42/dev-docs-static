TextRange
=========

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**IE Only**

This property is IE specific. Although it is well supported by IE, most other browsers no longer support this property. This property should only be used as one of the solutions when you need to be compatible with lower versions of IE, rather than relying on it completely in cross browser scripts.

A `TextRange` object represents a fragment of text in a document, similar to the standard defined [`Range`](range) interface.

This object is used to represent a specific piece of text in the document. For example, when you hold down the mouse to select the content on the page, you create a typical `TextRange`. It is implemented in IE, then a `TextRange` object can be created by <span class="page-not-created">`Element.createTextRange()`</span> or <span class="page-not-created">`Document.selection.createRange()`</span>.

Note that this interface is not supported in non IE browsers. Alternative [`Selection`](selection) and [`Range`](range) interfaces can be used.

Properties
----------

 <span class="page-not-created">`TextRange.boundingHeight`</span><span class="badge inline readonly">Read only </span>   
Returns the height of the rectangle bound to the `TextRange` object.

 <span class="page-not-created">`TextRange.boundingLeft`</span><span class="badge inline readonly">Read only </span>   
Returns the distance between the left edge of the rectangle that binds the `TextRange` object and the left edge that completely contains the `TextRange` object.

 <span class="page-not-created">`TextRange.boundingTop`</span><span class="badge inline readonly">Read only </span>   
Returns the distance between the top edge of the rectangle that binds the `TextRange` object and the top edge that completely contains the `TextRange` object.

 <span class="page-not-created">`TextRange.boundingWidth`</span><span class="badge inline readonly">Read only </span>   
Returns the width of the rectangle bound to the `TextRange` object.

<span class="page-not-created">`TextRange.htmlText`</span>  
Gets or sets the HTML content within the `TextRange`.

<span class="page-not-created">`TextRange.text`</span>  
Gets or sets the plaintext content within the `TextRange`.

Methods
-------

<span class="page-not-created">`TextRange.collapse()`</span>  
Move the caret to the beginning or end of the current range.

<span class="page-not-created">`TextRange.duplicate()`</span>  
Returns a copy of `TextRange`.

<span class="page-not-created">`TextRange.execCommand()`</span>  
Executes a [command](document/execcommand) on the current document, the current selection, or the given scope.

<span class="page-not-created">`TextRange.expand()`</span>  
Expand the range to include the full range of specified units. For example, expanding a `"word"` means that the words at both ends of the range will completely included in the range. `xpand to wor` may become `expand to words`, etc.

<span class="page-not-created">`TextRange.findText()`</span>  
Searches the specified text in the original range and adjusts the range to include the first match.

<span class="page-not-created">`TextRange.inRange()`</span>  
Returns whether the current range contains the specified range.

<span class="page-not-created">`TextRange.isEqual()`</span>  
Returns whether the current range is equal to the specified range.

<span class="page-not-created">`TextRange.move()`</span>  
Collapses the range and moves the blank range by a specified number of units. Such as, `move("character",-1)` means to move one character to the left.

<span class="page-not-created">`TextRange.moveEnd()`</span>  
Moves the end of the range by a specified number of units.

<span class="page-not-created">`TextRange.moveStart()`</span>  
Moves the start of the range by a specified number of units.

<span class="page-not-created">`TextRange.moveToElementText()`</span>  
Causes the range to contain the text of the specified element. Can only be used on [`Element`](element) objects.

<span class="page-not-created">`TextRange.parentElement()`</span>  
Returns the parent element of the range, which is the smallest element that contains the range completely. If the selection contains more than one element, when you modify the contents of the selection, the contents will be placed in the corresponding position of the parent element instead of the child element.

<span class="page-not-created">`TextRange.pasteHTML()`</span>  
Paste the HTML content into the given range and replace any previous text and HTML elements in the range.

<span class="page-not-created">`TextRange.queryCommandEnabled()`</span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the specified command can be executed successfully with the `execCommand` method in the current state of the given document. You can also see [`Document.queryCommandEnabled()`](document/querycommandenabled).

<span class="page-not-created">`TextRange.queryCommandState()`</span>  
Returns the [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating the current state of the specified command. You can also see [`Document.queryCommandState()`](document/querycommandstate).

<span class="page-not-created">`TextRange.queryCommandValue()`</span>  
Returns the [`DOMString`](domstring) indicating the current value of the specified command. You can also see <span class="page-not-created">`Document.queryCommandValue()`</span>.

<span class="page-not-created">`TextRange.scrollIntoView()`</span>  
Scroll the range to the visible range (top or bottom). It can be used as an alternative to [`Element.scrollIntoView`](element/scrollintoview) in the lower version of IE.

<span class="page-not-created">`TextRange.select()`</span>  
Select the current range (i.e. the blue selection seen by the user).

<span class="page-not-created">`TextRange.setEndPoint()`</span>  
Sets the end point of the current range based on the bounds of other `TextRange`.

Example
-------

The following example is valid under IE9. The example gets the `TextRange` through `document.selection`, and sets the specified element to be selected. IE9 supports the standard alternative [`Range`](range).

    var range = document.selection.createRange();
    var element = document.getElementById("test");
    range.moveToElementText(element);
    range.select();
    // Selected "SomeTextToBeSelected"

    <!DOCTYPE html>
    <html>
    <head>
      <title>TextRange Example</title>
    </head>
    <body>
      <p id="test">SomeTextToBeSelected</p>
    </body>
    </html>

Notes
-----

### Use TextRange to Operate the Selection

Valid only under **IE9**. The [`selection`](selection) interface should be used first, if the browser allows it.

<span class="page-not-created">`document.selection`</span> property returns a non-standard `selection` object, and the `selection.createRange()` method creates a `TextRange` object consistent with the currently selection.

    var sel = document.selection;
    var range = sel.createRange();
    alert(range.text);
    // Output plaintext of the selection

Note that the `createRange` method does not create a reference. If you want to select the modified range after modifying the selection, you need to call the `TextRange.select` method.

### `selection` Compatibility

The `document.selection` object is the primary purpose of `TextRange`. This object is used to process the selected ranges in the document, and is mainly implemented by using the `TextRange` interface. According to the standard, a window / document may have multiple non adjacent selection, but only Firefox can select multiple ranges through Ctrl; generally, only one selected `TextRange` is allowed in ie.

However, in other browsers, `document` does not have a so-called `selection` attribute - they operate on the selection through the standard [Selection API](selection), that is, they get the `Selection` object through the `window.getselection()` method, and use the standard `Range` object to process the text fragment. IE9 and later also gave up the `document.selection` object and switched to the standard interface (although `TextRange` has been reserved, it has lost its function in most cases).

It's easy to get confused. Generally, if the script only needs to be compatible with the latest browser, the standard interface is the best choice; however, the current website still wants to be compatible with IE8 or below browsers. Therefore, the best way is to deal with both at the same time, that is, try to use `TextRange` mode when the standard interface is not supported, but do not regard it as the only choice.

Browser compatibility
---------------------

See also
--------

-   [`Selection`](selection) and [`Range`](range) standard interface
-   [Selection API](selection) to replace this non-standard interface

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextRange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextRange</a>
