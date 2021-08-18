# Notification.lang

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `lang` read-only property of the [`Notification`](../notification) interface indicates the language used in the notification, as specified in the `lang` option of the [`Notification()`](notification) constructor.

The language itself is specified using a [`DOMString`](../domstring) representing a [BCP 47 language tag](https://www.rfc-editor.org/rfc/bcp/bcp47.txt). See the Sitepoint [ISO 2 letter language codes](https://www.sitepoint.com/web-foundations/iso-2-letter-language-codes/) page for a simple reference.

## Syntax

    var language = Notification.lang;

### Value

A [`DOMString`](../domstring) specifying the language tag.

## Examples

The following snippet fires a notification; a simple `options` object is created, then the notification is fired using the `Notification()` constructor.

    var options = {
      body: 'Do you like my body?',
      lang: 'en-US'
    }

    var n = new Notification('Test notification',options);

    console.log(n.lang) // should return 'en-US'

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://notifications.spec.whatwg.org/#dom-notification-lang">Notifications API<br />
<span class="small">The definition of 'lang' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Living standard</td></tr></tbody></table>

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

`lang`

Yes

14

26

No

Yes

11

No

Yes

26

Yes

No

Yes

## See also

- [Using the Notifications API](../notifications_api/using_the_notifications_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Notification/lang" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Notification/lang</a>
