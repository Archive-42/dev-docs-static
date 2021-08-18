# Document.execCommand()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

When an HTML document has been switched to `designMode`, its `document` object exposes an `execCommand` method to run commands that manipulate the current editable region, such as [form inputs](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) or `contentEditable` elements.

Most commands affect the document's [selection](../selection) (bold, italics, etc.), while others insert new elements (adding a link), or affect an entire line (indenting). When using `contentEditable`, `execCommand()` affects the currently active editable element.

## Syntax

    document.execCommand(aCommandName, aShowDefaultUI, aValueArgument)

### Return value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `false` if the command is unsupported or disabled.

**Note**: `document.execCommand()` only returns `true` if it is invoked as part of a user interaction. You can't use it to verify browser support before calling a command. From Firefox 82, nested `document.execCommand()` calls will always return `false`.

### Parameters

`aCommandName`  
A [`DOMString`](../domstring) specifying the name of the command to execute. See [Commands](#commands) for a list of possible commands.

`aShowDefaultUI`  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the default user interface should be shown. This is not implemented in Mozilla.

`aValueArgument`  
For commands which require an input argument, is a [`DOMString`](../domstring) providing that information. For example, `insertImage` requires the URL of the image to insert. Specify `null` if no argument is needed.

### Commands

`backColor`  
Changes the document background color. In `styleWithCss` mode, it affects the background color of the containing block instead. This requires a [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) value string to be passed in as a value argument. Note that Internet Explorer uses this to set the text background color.

`bold`  
Toggles bold on/off for the selection or at the insertion point. Internet Explorer uses the [`<strong>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strong) tag instead of [`<b>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/b).

`ClearAuthenticationCache`  
Clears all authentication credentials from the cache.

`contentReadOnly`  
Makes the content document either read-only or editable. This requires a boolean true/false as the value argument. (Not supported by Internet Explorer.)

`copy`  
Copies the current selection to the clipboard. Conditions of having this behavior enabled vary from one browser to another, and have evolved over time. Check the compatibility table to determine if you can use it in your case.

`createLink`  
Creates an hyperlink from the selection, but only if there is a selection. Requires a [URI](https://developer.mozilla.org/en-US/docs/Archive/Mozilla/URIs_and_URLs) string as a value argument for the hyperlink's `href`. The URI must contain at least a single character, which may be whitespace. (Internet Explorer will create a link with a `null` value.)

`cut`  
Removes the current selection and copies it to the clipboard. When this behavior is enabled varies between browsers, and its conditions have evolved over time. Check [the compatibility table](#browser_compatibility) for usage details.

`decreaseFontSize`  
Adds a [`<small>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/small) tag around the selection or at the insertion point. (Not supported by Internet Explorer.)

`defaultParagraphSeparator`  
Changes the paragraph separator used when new paragraphs are created in editable text regions. See [Differences in markup generation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Editable_content#differences_in_markup_generation) for more details.

`delete`  
Deletes the current selection.

`enableAbsolutePositionEditor`  
Enables or disables the grabber that allows absolutely-positioned elements to be moved around. The grabber is disabled by default since Firefox 64 ([bug 1490641](https://bugzilla.mozilla.org/show_bug.cgi?id=1490641)).

`enableInlineTableEditing`  
Enables or disables the table row/column insertion and deletion controls. The controls are disabled by default since Firefox 64 ([bug 1490641](https://bugzilla.mozilla.org/show_bug.cgi?id=1490641)).

`enableObjectResizing`  
Enables or disables the resize handles on images, tables, and absolutely-positioned elements and other resizable objects. The handles are disabled by default since Firefox 64 ([bug 1490641](https://bugzilla.mozilla.org/show_bug.cgi?id=1490641)).

`fontName`  
Changes the font name for the selection or at the insertion point. This requires a font name string (like `"Arial"`) as a value argument.

`fontSize`  
Changes the font size for the selection or at the insertion point. This requires an integer from `1`-`7` as a value argument.

`foreColor`  
Changes a font color for the selection or at the insertion point. This requires a hexadecimal color value string as a value argument.

`formatBlock`  
Adds an HTML block-level element around the line containing the current selection, replacing the block element containing the line if one exists (in Firefox, [`<blockquote>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote) is the exception — it will wrap any containing block element). Requires a tag-name string as a value argument. Virtually all block-level elements can be used. (Internet Explorer and Edge support only heading tags `H1`–`H6`, `ADDRESS`, and `PRE`, which must be wrapped in angle brackets, such as `"<H1>"`.)

`forwardDelete`  
Deletes the character ahead of the [cursor](https://en.wikipedia.org/wiki/Cursor_%28computers%29)'s position, identical to hitting the Delete key on a Windows keyboard.

`heading`  
Adds a heading element around a selection or insertion point line. Requires the tag-name string as a value argument (i.e. `"H1"`, `"H6"`). (Not supported by Internet Explorer and Safari.)

`hiliteColor`  
Changes the background color for the selection or at the insertion point. Requires a color value string as a value argument. `useCSS` must be `true` for this to function. (Not supported by Internet Explorer.)

`increaseFontSize`  
Adds a [`<big>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/big) tag around the selection or at the insertion point. (Not supported by Internet Explorer.)

`indent`  
Indents the line containing the selection or insertion point. In Firefox, if the selection spans multiple lines at different levels of indentation, only the least indented lines in the selection will be indented.

`insertBrOnReturn`  
Controls whether the Enter key inserts a [`<br>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br) element, or splits the current block element into two. (Not supported by Internet Explorer.)

`insertHorizontalRule`  
Inserts a [`<hr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/hr) element at the insertion point, or replaces the selection with it.

`insertHTML`  
Inserts an HTML string at the insertion point (deletes selection). Requires a valid HTML string as a value argument. (Not supported by Internet Explorer.)

`insertImage`  
Inserts an image at the insertion point (deletes selection). Requires a URL string for the image's `src` as a value argument. The requirements for this string are the same as `createLink`.

`insertOrderedList`  
Creates a [numbered ordered list](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol) for the selection or at the insertion point.

`insertUnorderedList`  
Creates a [bulleted unordered list](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) for the selection or at the insertion point.

`insertParagraph`  
Inserts a [paragraph](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) around the selection or the current line. (Internet Explorer inserts a paragraph at the insertion point and deletes the selection.)

`insertText`  
Inserts the given plain text at the insertion point (deletes selection).

`italic`  
Toggles italics on/off for the selection or at the insertion point. (Internet Explorer uses the [`<em>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/em) element instead of [`<i>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/i).)

`justifyCenter`  
Centers the selection or insertion point.

`justifyFull`  
Justifies the selection or insertion point.

`justifyLeft`  
Justifies the selection or insertion point to the left.

`justifyRight`  
Right-justifies the selection or the insertion point.

`outdent`  
Outdents the line containing the selection or insertion point.

`paste`  
Pastes the clipboard contents at the insertion point (replaces current selection). Disabled for web content.

`redo`  
Redoes the previous undo command.

`removeFormat`  
Removes all formatting from the current selection.

`selectAll`  
Selects all of the content of the editable region.

`strikeThrough`  
Toggles strikethrough on/off for the selection or at the insertion point.

`subscript`  
Toggles [subscript](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sub) on/off for the selection or at the insertion point.

`superscript`  
Toggles [superscript](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sup) on/off for the selection or at the insertion point.

`underline`  
Toggles [underline](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/u) on/off for the selection or at the insertion point.

`undo`  
Undoes the last executed command.

`unlink`  
Removes the [anchor element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) from a selected hyperlink.

`useCSS` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Toggles the use of HTML tags or CSS for the generated markup. Requires a boolean true/false as a value argument.

NOTE: This argument is logically backwards (i.e. use `false` to use CSS, `true` to use HTML) and unsupported by Internet Explorer. This has been deprecated in favor of `styleWithCSS`.

`styleWithCSS`  
Replaces the `useCSS` command. `true` modifies/generates `style` attributes in markup, false generates presentational elements.

## Example

An example of [how to use it](https://codepen.io/chrisdavidmills/full/gzYjag/) on CodePen.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/editing/docs/execCommand/">execCommand</a></td><td>Unofficial Draft</td><td></td></tr></tbody></table>

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

`execCommand`

1

12

1

From Firefox 82, nested calls are not supported (return `false`). See [bug 1634262](https://bugzil.la/1634262).

4

9

1.3

1

18

4

From Firefox 82, nested calls are not supported (return `false`). See [bug 1634262](https://bugzil.la/1634262).

10.1

1

1.0

`ClearAuthenticationCache`

No

12-79

No

6

No

No

No

No

No

No

No

No

`copy`

42

12

41

9

29

10

42

42

41

29

10

4.0

`cut`

42

12

41

9

29

10

42

42

41

29

10

4.0

`defaultParagraphSeparator`

No

≤18-79

55

No

Yes

No

No

No

55

Yes

No

No

`insertBrOnReturn`

No

No

Yes

No

No

No

No

No

Yes

No

No

No

## See also

- [`HTMLElement.contentEditable`](../htmlelement/contenteditable)
- [`document.designMode`](designmode)
- [Rich-Text Editing in Mozilla](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Editable_content/Rich-Text_Editing_in_Mozilla)
- [Scribe's "Browser Inconsistencies" documentation](https://github.com/guardian/scribe/blob/master/BROWSERINCONSISTENCIES.md) with bugs related to `document.execCommand`.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/execCommand" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/execCommand</a>
