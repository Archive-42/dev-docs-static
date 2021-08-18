# DOMImplementation.createHTMLDocument()

The `DOMImplementation.createHTMLDocument()` method creates a new HTML [`Document`](../document).

## Syntax

    const newDoc = document.implementation.createHTMLDocument(title)

### Parameters

`title` <span class="badge inline optional">Optional</span> (except in IE)  
A [`DOMString`](../domstring) containing the title to give the new HTML document.

## Example

This example creates a new HTML document and inserts it into an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) in the current document.

Here's the HTML for this example:

    <body>
      <p>Click <a href="javascript:makeDocument()">here</a> to create a new document and insert it below.</p>
      <iframe id="theFrame" src="about:blank" />
    </body>

The JavaScript implementation of `makeDocument()` follows:

    function makeDocument() {
      let frame = document.getElementById("theFrame");

      let doc = document.implementation.createHTMLDocument("New Document");
      let p = doc.createElement("p");
      p.textContent = "This is a new paragraph.";

      try {
        doc.body.appendChild(p);
      } catch(e) {
        console.log(e);
      }

      // Copy the new HTML document into the frame

      let destDocument = frame.contentDocument;
      let srcNode = doc.documentElement;
      let newNode = destDocument.importNode(srcNode, true);

      destDocument.replaceChild(newNode, destDocument.documentElement);
    }

The code in lines 4–12 handle creating the new HTML document and inserting some content into it. Line 4 uses `createHTMLDocument()` to construct a new HTML document whose [`<title>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title) is `"New Document"`. Lines 5 and 6 create a new paragraph element with some simple content, and then lines 8–12 handle inserting the new paragraph into the new document.

Line 16 pulls the `contentDocument` of the frame; this is the document into which we'll be injecting the new content. The next two lines handle importing the contents of our new document into the new document's context. Finally, line 20 actually replaces the contents of the frame with the new document's contents.

[View Live Examples](https://media.prod.mdn.mozit.cloud/samples/domref/createHTMLDocument.html)

The returned document is pre-constructed with the following HTML:

    <!doctype html>
    <html>
    <head>
    <title>title</title>
    </head>
    <body>
    </body>
    </html>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-domimplementation-createhtmldocument">DOM<br />
<span class="small">The definition of 'DOMImplementation.createHTMLDocument' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`createHTMLDocument`

1

12

4

9

The `title` parameter is required, but can be empty string.

≤12.1

1

1

18

4

≤12.1

1

1.0

## See also

- The [`DOMImplementation`](../domimplementation) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementation/createHTMLDocument" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementation/createHTMLDocument</a>
