# Navigator.registerContentHandler()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Allows web sites to register themselves as possible handlers for content of a particular MIME type.

**Note**

Web sites may only register content handlers for themselves. For security reasons, it's not possible for an extension or web site to register content handlers targeting other sites.

## Syntax

    navigator.registerContentHandler(mimeType, uri, title);

- `mimeType` is the desired MIME type as a string.
- `uri` is the URI to the handler as a string.
- `title` is the title of the handler presented to the user as a string.

## Example

    navigator.registerContentHandler(
        "application/vnd.mozilla.maybe.feed",
        "http://www.example.tld/?foo=%s",
        "My Feed Reader"
    );

## Notes

For [Firefox 2](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Releases/2) and above, only the `application/vnd.mozilla.maybe.feed`, `application/atom+xml`, and `application/rss+xml` MIME types are supported. All values have the same effect, and the registered handler will receive feeds in all Atom and RSS versions (see [bug 391286](https://bugzilla.mozilla.org/show_bug.cgi?id=391286)).

Firefox is the only browser that implemented this feature, and it wasn't implemented to match the standard. This feature has since been removed from the HTML standard and shouldn't be used.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/html52/webappapis.html#dom-navigator-registercontenthandler">HTML 5.2<br />
<span class="small">The definition of 'registerContentHandler()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>This feature is present in HTML 5.2, but has since been removed from the WHATWG HTML Living Standard.</td></tr></tbody></table>

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

`registerContentHandler`

4-6

No

2-62

No

≤12.1-15

?

No

No

?

≤12.1-14

?

No

## See also

- [Web-based protocol handlers](registerprotocolhandler/web-based_protocol_handlers)
- [`Navigator.registerProtocolHandler()`](registerprotocolhandler)
- [Web activities](https://developer.mozilla.org/en-US/docs/WebAPI/Web_Activities), particularly view and open
- [XPCOM Interface Reference &gt; nsIWebContentHandlerRegistrar &gt; registerContentHandler](https://developer.mozilla.org/en-US/docs/Mozilla/Tech/XPCOM/Reference/Interface/nsIWebContentHandlerRegistrar#registerContentHandler) - This shows how to use this function XPCOM scope

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/registerContentHandler" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/registerContentHandler</a>
