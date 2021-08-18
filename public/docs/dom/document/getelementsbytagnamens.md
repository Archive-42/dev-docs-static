# Document.getElementsByTagNameNS()

Returns a list of elements with the given tag name belonging to the given namespace. The complete document is searched, including the root node.

## Syntax

    elements = document.getElementsByTagNameNS(namespace, name)

- elements is a live [`NodeList`](../nodelist) (but see the note below) of found elements in the order they appear in the tree.
- namespace is the namespace URI of elements to look for (see [`element.namespaceURI`](../element/namespaceuri)).
- name is either the local name of elements to look for or the special value `*`, which matches all elements (see [`element.localName`](../element/localname)).

**Note:** While the W3C specification says `elements` is a `NodeList`, this method returns a [`HTMLCollection`](../htmlcollection) both in Gecko and Internet Explorer. Opera returns a `NodeList`, but with a `namedItem` method implemented, which makes it similar to a `HTMLCollection`. As of January 2012, only in WebKit browsers is the returned value a pure `NodeList`. See [bug 14869](https://bugzilla.mozilla.org/show_bug.cgi?id=14869) for details.

**Note:** Currently parameters in this method are case-sensitive, but they were case-insensitive in Firefox 3.5 and before. See the [developer release note for Firefox 3.6](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Releases/3.6#dom) and a note in Browser compatibility section in [`Element.getElementsByTagNameNS`](../element/getelementsbytagnamens) for details.

## Example

In the following example `getElementsByTagNameNS` starts from a particular parent element, and searches topdown recursively through the DOM from that parent element, looking for child elements matching the tag `name` parameter.

Note that when the node on which `getElementsByTagName` is invoked is not the `document` node, in fact the [`element.getElementsByTagNameNS`](../element/getelementsbytagnamens) method is used.

To use the following example, just copy/paste it into a new file saved with the .xhtml extension.

    <html xmlns="http://www.w3.org/1999/xhtml">

    <head>
    <title>getElementsByTagNameNS example</title>

    <script type="text/javascript">

    function getAllParaElems()
    {
      var allParas = document.getElementsByTagNameNS("http://www.w3.org/1999/xhtml", "p");

      var num = allParas.length;

      alert("There are " + num + " &lt;p&gt; elements in this document");
    }

    function div1ParaElems()
    {
      var div1 = document.getElementById("div1")
      var div1Paras = div1.getElementsByTagNameNS("http://www.w3.org/1999/xhtml", "p");

      var num = div1Paras.length;

      alert("There are " + num + " &lt;p&gt; elements in div1 element");
    }

    function div2ParaElems()
    {
      var div2 = document.getElementById("div2")
      var div2Paras = div2.getElementsByTagNameNS("http://www.w3.org/1999/xhtml", "p");

      var num = div2Paras.length;

      alert("There are " + num + " &lt;p&gt; elements in div2 element");
    }

    </script>
    </head>

    <body style="border: solid green 3px">
    <p>Some outer text</p>
    <p>Some outer text</p>

      <div id="div1" style="border: solid blue 3px">
        <p>Some div1 text</p>
        <p>Some div1 text</p>
        <p>Some div1 text</p>

        <div id="div2" style="border: solid red 3px">
        <p>Some div2 text</p>
        <p>Some div2 text</p>
        </div>
      </div>

    <p>Some outer text</p>
    <p>Some outer text</p>

    <button onclick="getAllParaElems();">
     show all p elements in document</button><br />

    <button onclick="div1ParaElems();">
     show all p elements in div1 element</button><br />

    <button onclick="div2ParaElems();">
     show all p elements in div2 element</button>

    </body>
    </html>

## Potential Workaround for other browsers which do not support

If the desired browser did not support XPath, another approach (such as traversing the DOM through all its children, identifying all @xmlns instances, etc.) would be necessary to find all tags with the desired local name and namespace, but XPath is much faster. (To accommodate Explorer, one could call an XPath wrapper instead of the XPath in the function below (as Explorer supports XPath with a different API), such as [this wrapper class](https://www.davidflanagan.com/javascript5/display.php?n=21-10&f=21/10.js).)

    function getElementsByTagNameNSWrapper (ns, elName, doc, context) {
     if (!doc) {
      doc = document;
     }
     if (!context) {
      context = doc;
     }

     var result = doc.evaluate('//*[local-name()="'+elName+'" and namespace-uri() = "'+ns+'"]', context, null, XPathResult.ORDERED_NODE_SNAPSHOT_TYPE, null);

            var a = [];
            for(var i = 0; i < result.snapshotLength; i++) {
                a[i] = result.snapshotItem(i);
            }
            return a;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-getelementsbytagnamens">DOM<br />
<span class="small">The definition of 'document.getElementsByTagNameNS' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`getElementsByTagNameNS`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

## See also

- [`Element.getElementsByTagNameNS()`](../element/getelementsbytagnamens)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByTagNameNS" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByTagNameNS</a>
