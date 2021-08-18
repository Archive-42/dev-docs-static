# Document.currentScript

The `Document.currentScript` property returns the [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) element whose script is currently being processed and [isn't a JavaScript module](https://github.com/whatwg/html/issues/997). (For modules use [import.meta](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import.meta) instead.)

It's important to note that this will not reference the [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) element if the code in the script is being called as a callback or event handler; it will only reference the element while it's initially being processed.

## Syntax

    var curScriptElement = document.currentScript;

## Example

This example checks to see if the script is being executed asynchronously:

    if (document.currentScript.async) {
      console.log("Executing asynchronously");
    } else {
      console.log("Executing synchronously");
    }

[View Live Examples](https://media.prod.mdn.mozit.cloud/samples/html/currentScript.html)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/dom.html#dom-document-currentscript">HTML Living Standard<br />
<span class="small">The definition of 'Document.currentScript' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`currentScript`

29

12

4

No

16

6.1

≤37

29

4

16

8

2.0

## See also

- [import.meta](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import.meta)
- [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)
- [`document.onafterscriptexecute`](onafterscriptexecute)
- [`document.onbeforescriptexecute`](onbeforescriptexecute)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/currentScript" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/currentScript</a>
