# Document.write()

The `Document.write()` method writes a string of text to a document stream opened by [`document.open()`](open).

**Note**: Because `document.write()` writes to the document **stream**, calling `document.write()` on a closed (loaded) document automatically calls `document.open()`, [which will clear the document](open#notes).

## Syntax

    document.write(markup);

### Parameters

markup  
A string containing the text to be written to the document.

### Example

    <html>

    <head>
      <title>Write example</title>

      <script>
        function newContent() {
          document.open();
          document.write("<h1>Out with the old, in with the new!</h1>");
          document.close();
        }
      </script>
    </head>

    <body onload="newContent();">
      <p>Some original document content.</p>
    </body>

    </html>

## Notes

The text you write is parsed into the document's structure model. In the example above, the `h1` element becomes a node in the document.

Writing to a document that has already loaded without calling [`document.open()`](open) will automatically call `document.open()`. After writing, call [`document.close()`](close) to tell the browser to finish loading the page.

If the `document.write()` call is embedded within an inline HTML `<script>` tag, then it will not call `document.open()`. For example:

    <script>
      document.write("<h1>Main title</h1>")
    </script>

**Note**: `document.write()` and [`document.writeln`](writeln) [do not work in XHTML documents](https://developer.mozilla.org/en-US/docs/Archive/Web/Writing_JavaScript_for_HTML) (you'll get an "Operation is not supported" \[`NS_ERROR_DOM_NOT_SUPPORTED_ERR`\] error in the error console). This happens when opening a local file with the .xhtml file extension or for any document served with an `application/xhtml+xml` [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type). More information is available in the [W3C XHTML FAQ](https://www.w3.org/MarkUp/2004/xhtml-faq#docwrite).

**Note**: Using `document.write()` in [deferred](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script#attr-defer) or [asynchronous](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script#attr-async) scripts will be ignored and you'll get a message like "A call to `document.write()` from an asynchronously-loaded external script was ignored" in the error console.

**Note**: In Edge only, calling `document.write()` more than once in an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) causes the error "SCRIPT70: Permission denied".

**Note**: Starting with version 55, Chrome will not execute `<script>` elements injected via `document.write()` when specific conditions are met. For more information, refer to [Intervening against document.write()](https://developers.google.com/web/updates/2016/08/removing-document-write).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-document-write">HTML Living Standard<br />
<span class="small">The definition of 'document.write(...)' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-75233634">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'document.write(...)' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr></tbody></table>

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

`write`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

## See also

- [`element.innerHTML`](../element/innerhtml)
- [`document.createElement()`](createelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/write" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/write</a>
