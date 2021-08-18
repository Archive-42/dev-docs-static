# Document.onbeforescriptexecute

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Fired when the code in a [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) element declared in an HTML document is about to start executing. Does not fire if the element is added dynamically, eg with appendChild().

## Syntax

    document.onbeforescriptexecute = funcRef;

_funcRef_ is a function reference, called when the event is fired. The event's `target` attribute is set to the script [`Element`](../element) that is about to be executed.

## Example

    function starting(e) {
      logMessage("Starting script with ID: " + e.target.id);
    }

    document.addEventListener("beforescriptexecute", starting, true);

[View Live Examples](https://media.prod.mdn.mozit.cloud/samples/html/currentScript.html)

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

`onbeforescriptexecute`

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

- [`Document.onafterscriptexecute`](onafterscriptexecute)
- [`Document.currentScript`](currentscript)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/onbeforescriptexecute" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/onbeforescriptexecute</a>
