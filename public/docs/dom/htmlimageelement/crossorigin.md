# HTMLImageElement.crossOrigin

The [`HTMLImageElement`](../htmlimageelement) interface's `crossOrigin` attribute is a string which specifies the Cross-Origin Resource Sharing ([CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS)) setting to use when retrieving the image.

## Syntax

    htmlImageElement.crossOrigin = crossOriginMode;
    let crossOriginMode = htmlImageElement.crossOrigin;

### Value

A [`DOMString`](../domstring) of a keyword specifying the CORS mode to use when fetching the image resource. If you don't specify `crossOrigin`, the image is fetched without CORS (the fetch `no-cors` mode).

Permitted values are:

`anonymous`  
Requests by the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element have their [`mode`](../request/mode) set to `cors` and their [`credentials`](../request/credentials) mode set to `same-origin`. This means that CORS is enabled and credentials are sent _if_ the image is fetched from the same origin from which the document was loaded.

`use-credentials`  
Requests by the [`HTMLImageElement`](../htmlimageelement) will use the `cors` mode and the `include` credentials mode; all image requests by the element will use CORS, regardless of what domain the fetch is from.

If `crossOrigin` is an empty string (`""`), the `anonymous` mode is selected.

## Example

In this example, a new [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element is created and added to the document, loading the image with the Anonymous state; the image will be loaded using CORS and credentials will be used for all cross-origin loads.

### JavaScript

The code below demonstrates setting the `crossOrigin` property on an `<img>` element to configure CORS access for the fetch of a newly-created image.

    const imageUrl = "https://mdn.mozillademos.org/files/16797/clock-demo-400px.png";
    const container = document.querySelector(".container");

    function loadImage(url) {
      const image = new Image(200, 200);
      image.addEventListener("load",
        () => container.prepend(image)
      );

      image.addEventListener("error", () => {
        const errMsg = document.createElement("output");
        errMsg.value = `Error loading image at ${url}`;
        container.append(errMsg);
      });

      image.crossOrigin = "anonymous";
      image.alt = "";
      image.src = url;
    }

    loadImage(imageUrl);

### HTML

    <div class="container">
      <p>Here's a paragraph. It's a very interesting paragraph. You
      are captivated by this paragraph. Keep reading this paragraph.
      Okay, now you can stop reading this paragraph. Thanks for
      reading me.</p>
    </div>

### CSS

    body {
      font: 1.125rem/1.5, Helvetica, sans-serif;
    }

    .container {
      display: flow-root;
      width: 37.5em;
      border: 1px solid #d2d2d2;
    }

    img {
      float: left;
      padding-right: 1.5em;
    }

    output {
      background: rgba(100, 100, 100, 0.1);
      font-family: Courier, monospace;
      width: 95%;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-img-crossorigin">HTML Living Standard<br />
<span class="small">The definition of 'HTMLImageElement.crossOrigin' in that specification.</span></a></td><td><span class="spec-">Unknown</span></td><td></td></tr></tbody></table>

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

`crossOrigin`

13

12

8

11

≤12.1

6

≤37

Yes

8

≤12.1

6

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/crossOrigin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/crossOrigin</a>
