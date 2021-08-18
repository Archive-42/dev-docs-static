# Document.open()

The `Document.open()` method opens a document for [writing](write).

This does come with some side effects. For example:

- All event listeners currently registered on the document, nodes inside the document, or the document's window are removed.
- All existing nodes are removed from the document.

## Syntax

    document.open();

### Parameters

None.

### Return value

A `Document` object instance.

## Examples

The following simple code opens the document and replaces its content with a number of different HTML fragments, before closing it again.

    document.open();
    document.write("<p>Hello world!</p>");
    document.write("<p>I am a fish</p>");
    document.write("<p>The number is 42</p>");
    document.close();

## Notes

An automatic `document.open()` call happens when [`document.write()`](write) is called after the page has loaded.

For years Firefox and Internet Explorer additionally erased all JavaScript variables, etc., in addition to removing all nodes. This is no longer the case.<span class="comment">document non-spec'ed parameters to document.open</span>

### Gecko-specific notes

Starting with Gecko 1.9, this method is subject to the same same-origin policy as other properties, and does not work if doing so would change the document's origin.

Starting with Gecko 1.9.2, `document.open()` uses the [principal](https://developer.mozilla.org/docs/Security_check_basics) of the document whose URI it uses, instead of fetching the principal off the stack. As a result, you can no longer call [`document.write()`](write) into an untrusted document from chrome, even using <a href="https://developer.mozilla.org/en-US/docs/wrappedJSObject" class="internal"><code>wrappedJSObject</code></a>. See [Security check basics](https://developer.mozilla.org/en-US/docs/Security_check_basics) for more about principals.

## Three-argument document.open()

There is a lesser-known and little-used three-argument version of `document.open()` , which is an alias of [`Window.open()`](../window/open) (see its page for full details).

This call, for example opens github.com in a new window, with its opener set to `null`:

    document.open('https://www.github.com','', 'noopener=true')

## Two-argument document.open()

Browsers used to support a two-argument `document.open()`, with the following signature:

    document.open(type, replace)

Where `type` specified the MIME type of the data you are writing (e.g. `text/html`) and replace if set (i.e. a string of `"replace"`) specified that the history entry for the new document would replace the current history entry of the document being written to.

This form is now obsolete; it won't throw an error, but instead just forwards to `document.open()` (i.e. is the equivalent of just running it with no arguments). The history-replacement behavior now always happens.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-document-open">HTML Living Standard<br />
<span class="small">The definition of 'document.open()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-72161170">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'document.open()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr></tbody></table>

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

`open`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

1

4

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

4

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

## See also

- [`Document`](../document)
- [`Window.open()`](../window/open)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/open" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/open</a>
