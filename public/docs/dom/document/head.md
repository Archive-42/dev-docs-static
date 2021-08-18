# Document.head

The `head` read-only property of the [`Document`](../document) interface returns the [`<head>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head) element of the current document.

## Syntax

    var objRef = document.head;

### Value

An [`HTMLHeadElement`](../htmlheadelement).

## Example

    <!doctype html>
    <head id="my-document-head">
      <title>Example: using document.head</title>
    </head>

    <script>
      var theHead = document.head;

      console.log(theHead.id); // "my-document-head";

      console.log( theHead === document.querySelector("head") ); // true
    </script>

## Notes

`document.head` is read-only. Trying to assign a value to this property will fail silently or, in [Strict Mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode), throws a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) .

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/html51/dom.html#dom-document-head">HTML 5.1<br />
<span class="small">The definition of 'Document.head' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/dom.html#dom-document-head">HTML5<br />
<span class="small">The definition of 'Document.head' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/dom.html#dom-document-head">HTML Living Standard<br />
<span class="small">The definition of 'Document.head' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`head`

4

12

4

9

11

5

≤37

Yes

4

Yes

4

Yes

## See also

- [`document.body`](body)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/head" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/head</a>
