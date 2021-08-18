HTMLImageElement.loading
========================

The [`HTMLImageElement`](../htmlimageelement) property `loading` is a string whose value provides a hint to the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) on how to handle the loading of the image which is currently outside the window's [visual viewport](https://developer.mozilla.org/en-US/docs/Glossary/Visual_Viewport). This helps to optimize the loading of the document's contents by postponing loading the image until it's expected to be needed, rather than immediately during the initial page load.

Syntax
------

    let imageLoadScheduling = htmlImageElement.loading;
    htmlImageElement.loading = eagerOrLazy;

### Value

A [`DOMString`](../domstring) providing a hint to the user agent as to how to best schedule the loading of the image to optimize page performance. The possible values are:

`eager`  
The default behavior, `eager` tells the browser to load the image as soon as the `<img>` element is processed.

`lazy`  
Tells the user agent to hold off on loading the image until the browser estimates that it will be needed imminently. For instance, if the user is scrolling through the document, a value of `lazy` will cause the image to only be loaded shortly before it will appear in the window's [visual viewport](https://developer.mozilla.org/en-US/docs/Glossary/Visual_Viewport).

Usage notes
-----------

### Timing of the load event

The [`load`](../window/load_event) event is fired when the document has been fully processed. When images are loaded eagerly (which is the default), every image in the document must be fetched before the `load` event can fire.

By specifying the value `lazy` for `loading`, you prevent the image from delaying the `load` attribute by the amount of time it takes to request, fetch, and process the image.

Images whose `loading` attribute is set to `lazy` but are located within the visual viewport immediately upon initial page load are loaded as soon as the layout is known, but their loads do not delay the firing of the `load` event. In other words, these images aren't loaded immediately when processing the `<img>` element, but are still loaded as part of the initial page load. They just don't affect the timing of the `load` event.

That means that when `load` fires, it's possible that any lazy-loaded images located in the visual viewport may not yet be visible.

### Preventing element shift during image lazy loads

When an image whose loading has been delayed by the `loading` attribute being set to `lazy` is finally loaded, the browser will determine the final size of the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element based on the style and intrinsic size of the image, then reflow the document as needed to update the positions of elements based on any size change made to the element to fit the image.

To prevent this reflow from occurring, you should explicitly specify the size of the image's presentation using the image element's [`width`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-width) and [`height`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-height) attributes. By establishing the intrinsic aspect ratio in this manner, you prevent elements from shifting around while the document loads, which can be disconcerting or offputting at best and can cause users to click the wrong thing at worst, depending on the exact timing of the deferred loads and reflows.

Example
-------

The `addImageToList()` function shown below adds a photo thumbnail to a list of items, using lazy-loading to avoid loading the image from the network until it's actually needed.

    function addImageToList(url) {
      const list = document.querySelector("div.photo-list");

      let newItem = document.createElement("div");
      newItem.className = "photo-item";

      let newImg = document.createElement("img");
      newImg.loading = "lazy";
      newImg.width = 320;
      newImg.height = 240;
      newImg.src = url;

      newItem.appendChild(newImg);
      list.appendChild(newItem);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#attr-img-loading">HTML Living Standard<br />
<span class="small">The definition of 'HTMLImageElement.loading' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`loading`

77

79

75

No

64

No

See [bug 196698](https://webkit.org/b/196698)

77

77

79

55

No

See [bug 196698](https://webkit.org/b/196698)

12.0

See also
--------

-   The [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element
-   [Web performance](https://developer.mozilla.org/en-US/docs/Learn/Performance) in the MDN Learning Area
-   [Lazy loading](https://developer.mozilla.org/en-US/docs/Web/Performance/Lazy_loading) in the MDN web performance guide
-   [Use lazy loading for images](#) in [Tips for authoring fast-loading HTML pages](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Author_fast-loading_HTML_pages)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/loading" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/loading</a>
