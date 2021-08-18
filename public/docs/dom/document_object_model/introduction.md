# Introduction to the DOM

The **Document Object Model** (**DOM**) is the data representation of the objects that comprise the structure and content of a document on the web. In this guide, we'll briefly introduce the DOM. We'll look at how the DOM represents an [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML) or [XML](https://developer.mozilla.org/en-US/docs/Glossary/XML) document in memory and how you use APIs to create web content and applications.

## What is the DOM?

The Document Object Model (DOM) is a programming interface for HTML and XML documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects. That way, programming languages can connect to the page.

A Web page is a document. This document can be either displayed in the browser window or as the HTML source. But it is the same document in both cases. The Document Object Model (DOM) represents that same document so it can be manipulated. The DOM is an object-oriented representation of the web page, which can be modified with a scripting language such as JavaScript.

The [W3C DOM](https://www.w3.org/DOM/) and [WHATWG DOM](https://dom.spec.whatwg.org) standards are implemented in most modern browsers. Many browsers extend the standard, so care must be exercised when using them on the web where documents may be accessed by various browsers with different DOMs.

For example, the standard DOM specifies that the `querySelectorAll` method in the code below must return a list of all the `<p>` elements in the document:

    const paragraphs = document.querySelectorAll("p");
    // paragraphs[0] is the first <p> element
    // paragraphs[1] is the second <p> element, etc.
    alert(paragraphs[0].nodeName);

All of the properties, methods, and events available for manipulating and creating web pages are organized into objects (for example, the `document` object that represents the document itself, the `table` object that implements the special [`HTMLTableElement`](../htmltableelement) DOM interface for accessing HTML tables, and so forth). This documentation provides an object-by-object reference to the DOM.

The modern DOM is built using multiple APIs that work together. The core [DOM](../document_object_model) defines the objects that fundamentally describe a document and the objects within it. This is expanded upon as needed by other APIs that add new features and capabilities to the DOM. For example, the [HTML DOM API](../html_dom_api) adds support for representing HTML documents to the core DOM.

## DOM and JavaScript

The short example above, like nearly all of the examples in this reference, is [JavaScript](https://developer.mozilla.org/en-US/docs/Glossary/JavaScript). That is to say, it's _written_ in JavaScript, but it _uses_ the DOM to access the document and its elements. The DOM is not a programming language, but without it, the JavaScript language wouldn't have any model or notion of web pages, HTML documents, XML documents, and their component parts (e.g. elements). Every element in a document—the document as a whole, the head, tables within the document, table headers, text within the table cells—is part of the document object model for that document, so they can all be accessed and manipulated using the DOM and a scripting language like JavaScript.

In the beginning, JavaScript and the DOM were tightly intertwined, but eventually, they evolved into separate entities. The page content is stored in the DOM and may be accessed and manipulated via JavaScript, so that we may write this approximative equation:

API = DOM + JavaScript

The DOM was designed to be independent of any particular programming language, making the structural representation of the document available from a single, consistent API. Though we focus exclusively on JavaScript in this reference documentation, implementations of the DOM can be built for any language, as this Python example demonstrates:

    # Python DOM example
    import xml.dom.minidom as m
    doc = m.parse(r"C:\Projects\Py\chap1.xml")
    doc.nodeName # DOM property of document object
    p_list = doc.getElementsByTagName("para")

For more information on what technologies are involved in writing JavaScript on the web, see [JavaScript technologies overview](https://developer.mozilla.org/en-US/docs/Web/JavaScript/JavaScript_technologies_overview).

## Accessing the DOM

You don't have to do anything special to begin using the DOM. Different browsers have different implementations of the DOM, and these implementations exhibit varying degrees of conformance to the actual DOM standard (a subject we try to avoid in this documentation), but every web browser uses some document object model to make web pages accessible via JavaScript.

When you create a script–whether it's inline in a `<script>` element or included in the web page by means of a script loading instruction–you can immediately begin using the API for the [`document`](../document) or [`window`](../window) elements to manipulate the document itself or to get at the children of that document, which are the various elements in the web page. Your DOM programming may be something as simple as the following, which displays an alert message by using the [`alert()`](../window/alert) function from the [`window`](../window) object, or it may use more sophisticated DOM methods to actually create new content, as in the longer example below.

This following JavaScript will display an alert when the document is loaded (and when the whole DOM is available for use):

    <body onload="window.alert('Welcome to my home page!');">

Another example. This function creates a new H1 element, adds text to that element, and then adds the `H1` to the tree for this document:

    <html>
      <head>
        <script>
           // run this function when the document is loaded
           window.onload = function() {

             // create a couple of elements in an otherwise empty HTML page
             const heading = document.createElement("h1");
             const heading_text = document.createTextNode("Big Head!");
             heading.appendChild(heading_text);
             document.body.appendChild(heading);
          }
        </script>
      </head>
      <body>
      </body>
    </html>

## Fundamental data types

This reference tries to describe the various objects and types in simple terms. But there are a number of different data types being passed around the API that you should be aware of.

**Note:** Because the vast majority of code that uses the DOM revolves around manipulating HTML documents, it's common to refer to the nodes in the DOM as **elements**, although strictly speaking not every node is an element.

The following table briefly describes these data types.

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Data type (Interface)</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><a href="../document"><code>Document</code></a></td><td>When a member returns an object of type <code>document</code> (e.g., the <code>ownerDocument</code> property of an element returns the <code>document</code> to which it belongs), this object is the root <code>document</code> object itself. The <a href="../document">DOM <code>document</code> Reference</a> chapter describes the <code>document</code> object.</td></tr><tr class="even"><td><a href="../node"><code>Node</code></a></td><td>Every object located within a document is a node of some kind. In an HTML document, an object can be an element node but also a text node or attribute node.</td></tr><tr class="odd"><td><a href="../element"><code>Element</code></a></td><td>The <code>element</code> type is based on <code>node</code>. It refers to an element or a node of type <code>element</code> returned by a member of the DOM API. Rather than saying, for example, that the <a href="../document/createelement"><code>document.createElement()</code></a> method returns an object reference to a <code>node</code>, we just say that this method returns the <code>element</code> that has just been created in the DOM. <code>element</code> objects implement the DOM <code>Element</code> interface and also the more basic <code>Node</code> interface, both of which are included together in this reference. In an HTML document, elements are further enhanced by the HTML DOM API's <a href="../htmlelement"><code>HTMLElement</code></a> interface as well as other interfaces describing capabilities of specific kinds of elements (for instance, <a href="../htmltableelement"><code>HTMLTableElement</code></a> for <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table"><code>&lt;table&gt;</code></a> elements).</td></tr><tr class="even"><td><a href="../nodelist"><code>NodeList</code></a></td><td>A <code>nodeList</code> is an array of elements, like the kind that is returned by the method <a href="../document/queryselectorall"><code>document.querySelectorAll()</code></a>. Items in a <code>nodeList</code> are accessed by index in either of two ways:<ul><li>list.item(1)</li><li>list[1]</li></ul>These two are equivalent. In the first, <code>item()</code> is the single method on the <code>nodeList</code> object. The latter uses the typical array syntax to fetch the second item in the list.</td></tr><tr class="odd"><td><span class="page-not-created"><code>Attribute</code></span></td><td>When an <code>attribute</code> is returned by a member (e.g., by the <code>createAttribute()</code> method), it is an object reference that exposes a special (albeit small) interface for attributes. Attributes are nodes in the DOM just like elements are, though you may rarely use them as such.</td></tr><tr class="even"><td><a href="../namednodemap"><code>NamedNodeMap</code></a></td><td>A <code>namedNodeMap</code> is like an array, but the items are accessed by name or index, though this latter case is merely a convenience for enumeration, as they are in no particular order in the list. A <code>namedNodeMap</code> has an <code>item()</code> method for this purpose, and you can also add and remove items from a <code>namedNodeMap</code>.</td></tr></tbody></table>

There are also some common terminology considerations to keep in mind. It's common to refer to any <span class="page-not-created">`Attribute`</span> node as an `attribute`, for example, and to refer to an array of DOM nodes as a `nodeList`. You'll find these terms and others to be introduced and used throughout the documentation.

## DOM interfaces

This guide is about the objects and the actual _things_ you can use to manipulate the DOM hierarchy. There are many points where understanding how these work can be confusing. For example, the object representing the HTML `form` element gets its `name` property from the `HTMLFormElement` interface but its `className` property from the `HTMLElement` interface. In both cases, the property you want is in that form object.

But the relationship between objects and the interfaces that they implement in the DOM can be confusing, and so this section attempts to say a little something about the actual interfaces in the DOM specification and how they are made available.

### Interfaces and Objects

Many objects borrow from several different interfaces. The table object, for example, implements a specialized [`HTMLTableElement`](../htmltableelement) interface, which includes such methods as `createCaption` and `insertRow`. But since it's also an HTML element, `table` implements the `Element` interface described in the DOM [`Element`](../element) Reference chapter. And finally, since an HTML element is also, as far as the DOM is concerned, a node in the tree of nodes that make up the object model for an HTML or XML page, the table object also implements the more basic `Node` interface, from which `Element` derives.

When you get a reference to a `table` object, as in the following example, you routinely use all three of these interfaces interchangeably on the object, perhaps without knowing it.

    const table = document.getElementById("table");
    const tableAttrs = table.attributes; // Node/Element interface
    for (let i = 0; i < tableAttrs.length; i++) {
      // HTMLTableElement interface: border attribute
      if(tableAttrs[i].nodeName.toLowerCase() == "border")
        table.border = "1";
    }
    // HTMLTableElement interface: summary attribute
    table.summary = "note: increased border";

### Core Interfaces in the DOM

This section lists some of the most commonly-used interfaces in the DOM. The idea is not to describe what these APIs do here but to give you an idea of the sorts of methods and properties you will see very often as you use the DOM. These common APIs are used in the longer examples in the [DOM Examples](examples) chapter at the end of this book.

The `document` and `window` objects are the objects whose interfaces you generally use most often in DOM programming. In simple terms, the `window` object represents something like the browser, and the `document` object is the root of the document itself. `Element` inherits from the generic `Node` interface, and together these two interfaces provide many of the methods and properties you use on individual elements. These elements may also have specific interfaces for dealing with the kind of data those elements hold, as in the `table` object example in the previous section.

The following is a brief list of common APIs in web and XML page scripting using the DOM.

- `document.querySelector(selector)`
- `document.querySelectorAll(name)`
- `document.createElement(name)`
- `parentNode.appendChild(node)`
- `element.innerHTML`
- `element.style.left`
- `element.setAttribute()`
- `element.getAttribute()`
- `element.addEventListener()`
- `window.content`
- `GlobalEventHandlers/onload`
- `window.scrollTo()`

## Testing the DOM API

This document provides samples for every interface that you can use in your own web development. In some cases, the samples are complete HTML pages, with the DOM access in a `<script>` element, the interface (e.g, buttons) necessary to fire up the script in a form, and the HTML elements upon which the DOM operates listed as well. When this is the case, you can cut and paste the example into a new HTML document, save it, and run the example from the browser.

There are some cases, however, when the examples are more concise. To run examples that only demonstrate the basic relationship of the interface to the HTML elements, you may want to set up a test page in which interfaces can be easily accessed from scripts. The following very simple web page provides a `<script>` element in the header in which you can place functions that test the interface, a few HTML elements with attributes that you can retrieve, set, or otherwise manipulate, and the web user interface necessary to call those functions from the browser.

You can use this test page or create a similar one to test the DOM interfaces you are interested in and see how they work on the browser platform. You can update the contents of the `test()` function as needed, create more buttons, or add elements as necessary.

    <html>
    <head>
      <title>DOM Tests</title>
      <script>
        function setBodyAttr(attr, value) {
          if (document.body) document.body[attr] = value;
          else throw new Error("no support");
        }
      </script>
    </head>
    <body>
      <div style="margin: .5in; height: 400px;">
        <p><b><code>text</code></b></p>
        <form>
          <select onChange="setBodyAttr('text',
            this.options[this.selectedIndex].value);">
            <option value="black">black</option>
            <option value="red">red</option>
          </select>
          <p><b><code>bgColor</code></b></p>
          <select onChange="setBodyAttr('bgColor',
            this.options[this.selectedIndex].value);">
            <option value="white">white</option>
            <option value="lightgrey">gray</option>
          </select>
          <p><b><code>link</code></b></p>
          <select onChange="setBodyAttr('link',
            this.options[this.selectedIndex].value);">
            <option value="blue">blue</option>
            <option value="green">green</option>
          </select>
          <small>
            <a href="http://some.website.tld/page.html" id="sample">
              (sample link)
            </a>
          </small><br />
          <input type="button" value="version" onclick="ver()" />
        </form>
      </div>
    </body>
    </html>

To test a lot of interfaces in a single page—for example, a "suite" of properties that affect the colors of a web page—you can create a similar test page with a whole console of buttons, textfields, and other HTML elements. The following screenshot gives you some idea of how interfaces can be grouped together for testing.

<figure><img src="data:image/gif;base64,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" alt="Figure 0.1 Sample DOM Test Page" width="199" height="375" /><figcaption>Figure 0.1 Sample DOM Test Page</figcaption></figure>In this example, the drop-down menus dynamically update such DOM—accessible aspects of the web page as its background color (`bgColor`), the color of the hyperlinks (`aLink`), and color of the text (`text`). However you design your test pages, testing the interfaces as you read about them is an important part of learning how to use the DOM effectively.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction</a>
