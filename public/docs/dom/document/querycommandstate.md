# Document.queryCommandState()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `queryCommandState()` method will tell you if the current selection has a certain [`Document.execCommand()`](execcommand) command applied.

## Syntax

    queryCommandState(String command)

### Parameters

`command` is a command from [`Document.execCommand()`](execcommand)

### Return value

`queryCommandState()` can return a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value or `null` if the state is unknown.

## Example

### HTML

    <div contenteditable="true">Select a part of this text!</div>
    <button onclick="makeBold();">Test the state of the 'bold' command</button>

### JavaScript

    function makeBold() {
      var state = document.queryCommandState("bold");
      switch (state) {
        case true:
          alert("The bold formatting will be removed from the selected text.");
          break;
        case false:
          alert("The selected text will be displayed in bold.");
          break;
        case null:
          alert("The state of the 'bold' command is indeterminable.");
          break;
      }
      document.execCommand('bold');
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/editing/execCommand.html#querycommandstate()">execCommand</a></td><td></td><td></td></tr></tbody></table>

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

`queryCommandState`

1

12

1

4

≤12.1

2

1

18

4

≤12.1

1

1.0

## See also

- [`HTMLElement.contentEditable`](../htmlelement/contenteditable)
- [`document.designMode`](designmode)
- [Rich-Text Editing in Mozilla](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Editable_content/Rich-Text_Editing_in_Mozilla)
- Browser bugs related to `queryCommandState()`: [Scribe's "Browser Inconsistencies" documentation](https://github.com/guardian/scribe/blob/master/BROWSERINCONSISTENCIES.md#documentquerycommandstate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/queryCommandState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/queryCommandState</a>
