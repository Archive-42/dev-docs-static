# Document.images

The `images` read-only property of the [`Document`](../document) interface returns a [collection](../htmlcollection) of the [images](../htmlimageelement/image) in the current HTML document.

## Syntax

    var imageCollection = document.images;

### Value

An [`HTMLCollection`](../htmlcollection) providing a live list of all of the images contained in the current document. Each entry in the collection is an [`HTMLImageElement`](../htmlimageelement) representing a single image element.

## Usage notes

You can use either JavaScript array notation or the [`item()`](../htmlcollection/item) method on the returned collection to access the items in the collection. The following are equivalent:

    firstImage = imageCollection.item(0);

    firstImage = imageCollection[0];

## Example

This example looks through the list of images and finds one whose name is `"banner.gif"`.

    var ilist = document.images;

    for(var i = 0; i < ilist.length; i++) {
        if(ilist[i].src == 'banner.gif') {
            // found the banner
        }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-document-images">HTML Living Standard<br />
<span class="small">The definition of 'Document.images' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-90379117">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'Document.images' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`images`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/images" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/images</a>
