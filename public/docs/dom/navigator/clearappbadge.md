# Navigator.clearAppBadge()

The `clearAppBadge()` method of the [`Navigator`](../navigator) interface clears a badge on the current app's icon by setting it to `nothing`. The value `nothing` indictes that no badge is currently set, and the status of the badge is _cleared_.

## Syntax

    let promise = Navigator.clearAppBadge();

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Exceptions

`NotSupportedError`  
The [`Navigator`](../navigator) does not have a document that this action can be acted on.

## Examples

Once all messages in an application have been read, call `clearAppBadge()` to clear the badge and remove the notification.

    navigator.clearAppBadge()

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/badging/#clearappbadge-method">Badging API<br />
<span class="small">The definition of 'clearAppBadge' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`clearAppBadge`

81

81

No

No

No

No

81

81

No

58

No

13.0

## See also

- [Badging for app icons](https://web.dev/badging-api/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/clearAppBadge" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/clearAppBadge</a>
