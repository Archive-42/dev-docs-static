# PageTransitionEvent.persisted

The `persisted` read-only property indicates if a webpage is loading from a cache.

## Syntax

    window.addEventListener('pageshow', function(event) {
      if (event.persisted) {
        console.log('Page was loaded from cache.');
      }
    });

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-pagetransitionevent-persisted">HTML Living Standard<br />
<span class="small">The definition of 'PageTransitionEvent: persisted' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`persisted`

Yes

12

Yes

11

The `persisted` property is known to be buggy in Internet Explorer. It is advised to check if `window.performance.navigation.type == 2` as well.

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PageTransitionEvent/persisted" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PageTransitionEvent/persisted</a>
