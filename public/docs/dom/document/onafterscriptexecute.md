# Document.onafterscriptexecute

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `Document.onafterscriptexecute` property references a function that fires when a static [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) element finishes executing its script. It does not fire if the element is added dynamically, such as with [`appendChild()`](../node/appendchild).

## Syntax

    document.onafterscriptexecute = funcRef;

funcRef is a function reference, called when the event is fired. The event's `target` attribute is set to the [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) element that just finished executing.

## Example

    function finished(e) {
      logMessage(`Finished script with ID: ${e.target.id}`);
    }

    document.addEventListener('afterscriptexecute', finished, true);

[View Live Example](https://media.prod.mdn.mozit.cloud/samples/html/currentScript.html)

## Specifications

- [HTML5](https://www.whatwg.org/specs/web-apps/current-work/#the-script-element)

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

`onafterscriptexecute`

No

No

9

No

No

No

No

No

9

No

No

No

## See also

- [`Document.onbeforescriptexecute`](onbeforescriptexecute)
- [`Document.currentScript`](currentscript)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/onafterscriptexecute" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/onafterscriptexecute</a>
