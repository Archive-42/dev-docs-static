# Document.readyState

The `Document.readyState` property describes the loading state of the [`document`](../document).

When the value of this property changes, a `readystatechange` event fires on the [`document`](../document) object.

## Syntax

    let string = document.readyState;

### Values

The `readyState` of a document can be one of following:

`loading`  
The [`document`](../document) is still loading.

`interactive`  
The document has finished loading and the document has been parsed but sub-resources such as scripts, images, stylesheets and frames are still loading.

`complete`  
The document and all sub-resources have finished loading. The state indicates that the `load` event is about to fire.

## Examples

### Different states of readiness

    switch (document.readyState) {
      case "loading":
        // The document is still loading.
        break;
      case "interactive":
        // The document has finished loading. We can now access the DOM elements.
        // But sub-resources such as scripts, images, stylesheets and frames are still loading.
        const span = document.createElement("span");
        span.textContent = "A <span> element.";
        document.body.appendChild(span);
        break;
      case "complete":
        // The page is fully loaded.
        console.log("The first CSS rule is: " + document.styleSheets[0].cssRules[0].cssText);
        break;
    }

### readystatechange as an alternative to DOMContentLoaded event

    // Alternative to DOMContentLoaded event
    document.onreadystatechange = function () {
      if (document.readyState === 'interactive') {
        initApplication();
      }
    }

### readystatechange as an alternative to load event

    // Alternative to load event
    document.onreadystatechange = function () {
      if (document.readyState === 'complete') {
        initApplication();
      }
    }

### readystatechange as event listener to insert or modify the DOM before DOMContentLoaded

    document.addEventListener('readystatechange', event => {
      if (event.target.readyState === 'interactive') {
        initLoader();
      }
      else if (event.target.readyState === 'complete') {
        initApp();
      }
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#current-document-readiness">HTML Living Standard<br />
<span class="small">The definition of 'Document readiness' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/#current-document-readiness">HTML 5.1<br />
<span class="small">The definition of 'Document readiness' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/#current-document-readiness">HTML5<br />
<span class="small">The definition of 'Document readiness' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`readyState`

1

12

3.6

11

9-11

Internet Explorer 9 and 10 have bugs where the 'interactive' state can be fired too early before the document has finished parsing.

4-9

Only supports 'complete'.

11

Opera Presto fires 'complete' late after the 'load' event (in an incorrect order as per HTML5 standard specification).

1

1

18

4

11

Opera Presto fires 'complete' late after the 'load' event (in an incorrect order as per HTML5 standard specification).

1

1.0

## See also

- `readystatechange` event
- `DOMContentLoaded` event
- `load` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/readyState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/readyState</a>
