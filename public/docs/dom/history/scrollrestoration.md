# History.scrollRestoration

The `scrollRestoration` property of [`History`](../history) interface allows web applications to explicitly set default scroll restoration behavior on history navigation.

## Syntax

    const scrollRestore = history.scrollRestoration

### Values

`auto`  
The location on the page to which the user has scrolled will be restored.

`manual`  
The location on the page is not restored. The user will have to scroll to the location manually.

## Examples

### Query the current scroll restoration behavior.

    const scrollRestoration = history.scrollRestoration
    if (scrollRestoration === 'manual') {
      console.log('The location on the page is not restored, user will need to scroll manually.');
    }

### Prevent automatic page location restoration

    if (history.scrollRestoration) {
      history.scrollRestoration = 'manual';
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#scroll-restoration-mode">HTML Living Standard<br />
<span class="small">The definition of 'scroll restoration mode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#dom-history-scrollrestoration">HTML5<br />
<span class="small">The definition of 'History.scrollRestoration' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`scrollRestoration`

46

79

46

No

33

11

46

46

46

33

11

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/History/scrollRestoration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/History/scrollRestoration</a>
