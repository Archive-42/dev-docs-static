# Using the W3C DOM Level 1 Core

The W3C's [DOM Level 1 Core](https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html) is an API for manipulating the DOM trees of HTML and XML documents (among other tree-like types of documents). Due to the ubiquity of the DOM, this API is supported in all major browsers, including Mozilla Firefox and Microsoft Internet Explorer, and serves as a base for scripting on the web.

## What is a DOM tree?

A [DOM](https://www.w3.org/TR/REC-DOM-Level-1/introduction.html) tree is a kind of [tree](https://en.wikipedia.org/wiki/Tree_structure) whose nodes represent an HTML or XML document's contents. Each HTML or XML document has a unique DOM tree representation. For example, the following document

    <html>
    <head>
      <title>My Document</title>
    </head>
    <body>
      <h1>Header</h1>
      <p>Paragraph</p>
    </body>
    </html>

has a DOM tree that looks like this:

<img src="data:image/jpeg;base64,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" width="290" height="190" />

(Note that, although the above tree is similar to the above document's DOM tree, it's not identical, as [the actual DOM tree preserves whitespace](../document_object_model/whitespace).)

When a web browser parses an HTML document, it builds a DOM tree and then uses it to display the document.

## What does the DOM Level 1 Core let me do?

The W3C DOM Level 1 Core allows you to change a DOM tree in _any way you want_. This implies the ability to create any HTML or XML document from scratch, or to change any contents of a given HTML or XML document. The easiest way for web page authors to edit the DOM of a document is to use JavaScript to access the `document` property of the global object. This `document` object implements the [Document interface](https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#i-Document) from the W3C's DOM Level 1 spec.

## A simple example

Suppose the author wants to change the header of the above document and write two paragraphs instead of one. The following script would do the job:

### HTML Content

    <body>
    <input type="button" value="Change this document." onclick="change()">
    <h2>Header</h2>
    <p>Paragraph</p>
    </body>

### JavaScript Content

    function change() {
        // document.getElementsByTagName("H2") returns a NodeList of the <h2>
        // elements in the document, and the first is number 0:

        var header = document.getElementsByTagName("H2").item(0);
        // the firstChild of the header is a Text node:
        header.firstChild.data = "A dynamic document";
        // now the header is "A dynamic document".

        var para = document.getElementsByTagName("P").item(0);
        para.firstChild.data = "This is the first paragraph.";

        // create a new Text node for the second paragraph
        var newText = document.createTextNode("This is the second paragraph.");
        // create a new Element to be the second paragraph
        var newElement = document.createElement("P");
        // put the text in the paragraph
        newElement.appendChild(newText);
        // and put the paragraph on the end of the document by appending it to
        // the BODY (which is the parent of para)
        para.parentNode.appendChild(newElement);
      }

You can see this script as [a complete example](using_the_w3c_dom_level_1_core/using_the_w3c_dom_level_1_core-doctree.jpg).

## How can I learn more?

Now that you are familiar with the basic concepts of the DOM, you may want to learn about the [DOM Level 1 fundamental methods](../document_object_model/traversing_an_html_table_with_javascript_and_dom_interfaces).

See also the [DOM Level 1 Core specification](https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html) from the W3C. It's a reasonably clear spec, although it is formal. The main thing that's useful to authors is the description of the different DOM objects and all their properties and methods. Also see our [other DOM documentation](../document_object_model).

**Original Document Information**

- Author(s): L. David Baron &lt;dbaron at dbaron dot org&gt;
- Copyright Information: ?? 1998-2005 by individual mozilla.org contributors; content available under a [Creative Commons license](https://www.mozilla.org/foundation/licensing/website-content.html)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document_object_model/Using_the_W3C_DOM_Level_1_Core" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document_object_model/Using_the_W3C_DOM_Level_1_Core</a>
