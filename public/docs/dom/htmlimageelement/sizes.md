# HTMLImageElement.sizes

The [`HTMLImageElement`](../htmlimageelement) property `sizes` allows you to specify the layout width of the image for each of a list of media conditions. This provides the ability to automatically select among different images—even images of different orientations or aspect ratios—as the document state changes to match different media conditions. Each condition is specified using the same conditional format used by [media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries).

## Syntax

    let sizes = htmlImageElement.sizes;
    htmlImageElement.sizes = sizes;

### Value

A [`USVString`](../usvstring) containing a comma-separated list of source size descriptors followed by an optional fallback size. Each **source size descriptor** is comprised of a media condition, then at least one whitespace character, then the **source size value** to use for the image when the media condition evaluates to `true`.

#### Media conditions

Each source size descriptor consists of a media condition as defined by the media queries standard. Because a source size descriptor is used to specify the width to use for the image during layout of the page, the media condition is typically (but not necessarily) based entirely on width information. See [Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries#syntax) in [Using media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) for details on how to construct a media condition.

#### Source size values

The source size value is a [CSS length](https://developer.mozilla.org/en-US/docs/Web/CSS/length). It may be specified using font-relative units (such as `em` or `ex`), absolute units (such as `px` or `cm`), or the `vw` unit, which lets you specify the width as a percentage of the viewport width (`1vw` being 1% of the viewport width).

**Note:** The source size value must _not_ be specified as a percentage of the container size; that is, lengths such as `50%` or `100%` are not allowed, as there would be uncertainty as to what the specified value is a percentage of.

## Example

In this example, a blog-like layout is created, displaying some text and an image which for which three size points are specified, depending on the width of the window. Three versions of the image are also available, with their widths specified. The browser takes all of this information and selects an image and width that best meets the specified values.

How exactly the images are used may depend upon the browser and what the pixel density of the user's display is.

Buttons at the bottom of the example let you actually modify the `sizes` property slightly, switching the largest of the three widths for the image between 40em and 50em.

### HTML

    <article>
      <h1>An amazing headline</h1>
      <div class="test"></div>
      <p>This is even more amazing content text. It's really spectacular.
         And fascinating. Oh, it's also clever and witty. Award-winning
         stuff, I'm sure.</p>
      <img src="/files/16870/new-york-skyline-wide.jpg"
           srcset="/files/16870/new-york-skyline-wide.jpg 3724w,
                   /files/16869/new-york-skyline-4by3.jpg 1961w,
                   /files/16871/new-york-skyline-tall.jpg 1060w"
           sizes="((min-width: 50em) and (max-width: 60em)) 50em,
                  ((min-width: 30em) and (max-width: 50em)) 30em,
                  (max-width: 30em) 20em">
      <p>Then there's even more amazing stuff to say down here. Can you
         believe it? I sure can't.</p>

      <button id="break40">Last Width: 40em</button>
      <button id="break50">Last Width: 50em</button>
    </article>

### CSS

    article {
      margin: 1em;
      max-width: 60em;
      min-width: 20em;
      height: 100vh;
      border: 4em solid #880E4F;
      border-radius: 7em;
      padding: 1.5em;
      font: 16px "Open Sans", Verdana, Arial, Helvetica, sans-serif;
    }

    article img {
      display: block;
      max-width: 100%;
      border: 1px solid #888;
      box-shadow: 0 0.5em 0.3em #888;
      margin-bottom: 1.25em;
    }

### JavaScript

The JavaScript code handles the two buttons that let you toggle the third width option between 40em and 50em; this is done by handling the [`click`](../element/click_event) event, using the JavaScript string object method [`replace()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace) to replace the relevant portion of the `sizes` string.

    let image = document.querySelector("article img");
    let break40 = document.getElementById("break40");
    let break50 = document.getElementById("break50");

    break40.addEventListener("click",
        event => image.sizes = image.sizes.replace(/50em,/, "40em,"));

    break50.addEventListener("click",
        event => image.sizes = image.sizes.replace(/40em,/, "50em,"));

### Result

This result may be [viewed in its own window](https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Web/API/HTMLImageElement/sizes/_samples_/Example).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-img-sizes">HTML Living Standard<br />
<span class="small">The definition of 'HTMLImageElement.sizes' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`sizes`

38

13

38

No

25

9

38

38

38

25

9

3.0

## See also

- [Media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries)
- [Using media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
- [Images in HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML)
- [Responsive images](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/sizes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/sizes</a>
