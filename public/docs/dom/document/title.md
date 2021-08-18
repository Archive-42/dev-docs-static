# Document.title

The `document.title` property gets or sets the current [title](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title) of the document.

## Syntax

    var docTitle = document.title;

docTitle is a string containing the document's title. If the title was overridden by setting `document.title`, it contains that value. Otherwise, it contains the title specified in the markup (see the [Notes](#notes) below).

    document.title = newTitle;

`newTitle` is the new title of the document. The assignment affects the return value of `document.title`, the title displayed for the document (e.g. in the titlebar of the window or tab), and it also affects the DOM of the document (e.g. the content of the `<title>` element in an HTML document).

## Example

    <!DOCTYPE html>
    <html>
    <head>
      <title>Hello World!</title>
    </head>
    <body>

      <script>
        alert(document.title); // displays "Hello World!"
        document.title = "Goodbye World!";
        alert(document.title); // displays "Goodbye World!"
      </script>

    </body>
    </html>

## Notes

This property applies to HTML, SVG, XUL, and other documents in Gecko.

For HTML documents the initial value of `document.title` is the text content of the `<title>` element. For XUL it's the value of the `title` attribute of the `<xul:window>` or other top-level XUL element.

In XUL, accessing `document.title` before the document is fully loaded has undefined behavior: `document.title` may return an empty string and setting `document.title` may have no effect.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#document.title">HTML Living Standard<br />
<span class="small">The definition of 'document.title' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`title`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/title" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/title</a>
