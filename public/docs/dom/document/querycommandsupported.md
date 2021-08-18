# Document.queryCommandSupported()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `Document.queryCommandSupported()` method reports whether or not the specified editor command is supported by the browser.

## Syntax

    isSupported = document.queryCommandSupported(command);

### Parameters

`command`  
The command for which to determine support.

### Return value

Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) which is `true` if the command is supported and `false` if the command isn't.

## Notes

The `'paste'` command return `false` not only if the feature is unavailable, but also if the script calling it has insufficient privileges to perform the action.

## Examples

    var flg = document.queryCommandSupported("SelectAll");

    if(flg) {
      // ...Do something
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/editing/execCommand.html#querycommandsupported()">execCommand</a></td><td></td><td></td></tr></tbody></table>

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

`queryCommandSupported`

1

12

41

1-41

`paste` argument incorrectly returned `true` when the paste feature was available but the calling script had insufficient privileges to actually perform the action.

4

≤12.1

2

1

18

41

4-41

`paste` argument incorrectly returned `true` when the paste feature was available but the calling script had insufficient privileges to actually perform the action.

≤12.1

1

1.0

## See also

- [`Document.execCommand()`](execcommand)
- [`Document.queryCommandEnabled()`](querycommandenabled)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/queryCommandSupported" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/queryCommandSupported</a>
