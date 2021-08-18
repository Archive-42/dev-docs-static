# LargestContentfulPaint

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `LargestContentfulPaint` interface of the Largest Contentful Paint API provides details about the largest image or text paint before user input on a web page. The timing of this paint is a good heuristic for when the main page content is available during load.

## Properties

`LargestContentfulPaint.element`  
The element that is the current largest contentful paint.

`LargestContentfulPaint.renderTime`  
The time the element was rendered to the screen. May not be available if the element is a cross-origin image loaded without the `Timing-Allow-Origin` header.

`LargestContentfulPaint.loadTime`  
The time the element was loaded.

`LargestContentfulPaint.size`  
The intrinsic size of the element returned as the area (width \* height).

`LargestContentfulPaint.id`  
The id of the element. This property returns an empty string when there is no id.

`LargestContentfulPaint.url`  
If the element is an image, the request url of the image.

## Methods

`LargestContentfulPaint.toJSON()`  
Returns the above properties as JSON.

## Examples

The following example shows how to create a [`PerformanceObserver`](performanceobserver) that listens for `largest-contentful-paint` entries and logs the LCP value to the console.

This example also demonstrates how to include buffered entries (those that ocurred before `observer()` was called), which is done by setting the `buffered` option to `true`.

Note that in this example data is only sent to the server when the user leaves the tab.

    // Catch errors since some browsers throw when using the new `type` option.
    // https://bugs.webkit.org/show_bug.cgi?id=209216
    try {
      let lcp;

      const po = new PerformanceObserver((entryList) => {
        const entries = entryList.getEntries();
        const lastEntry = entries[entries.length - 1];

        // Update `lcp` to the latest value, using `renderTime` if it's available,
        // otherwise using `loadTime`. (Note: `renderTime` may not be available on
        // image elements loaded cross-origin without the `Timing-Allow-Origin` header.)
        lcp = lastEntry.renderTime || lastEntry.loadTime;
      });

      po.observe({type: 'largest-contentful-paint', buffered: true});

      // Send data to the server.
      addEventListener('visibilitychange', function fn() {
        if (lcp && document.visibilityState === 'hidden') {
          console.log('LCP:', lcp);
          removeEventListener('visibilitychange', fn, true);
        }
      }, true);
    } catch (e) {
      // Do nothing if the browser doesn't support this API.
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/largest-contentful-paint/#sec-largest-contentful-paint-interface">Largest Contentful Paint<br />
<span class="small">The definition of 'LargestContentfulPaint' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`LargestContentfulPaint`

77

80

No

No

Yes

No

77

77

No

Yes

No

12.0

`element`

77

80

No

No

Yes

No

77

77

No

Yes

No

12.0

`id`

77

80

No

No

Yes

No

77

77

No

Yes

No

12.0

`loadTime`

77

80

No

No

Yes

No

77

77

No

Yes

No

12.0

`renderTime`

77

80

No

No

Yes

No

77

77

No

Yes

No

12.0

`size`

77

80

No

No

Yes

No

77

77

No

Yes

No

12.0

`toJSON`

77

80

No

No

Yes

No

77

77

No

Yes

No

12.0

`url`

77

80

No

No

Yes

No

77

77

No

Yes

No

12.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LargestContentfulPaint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LargestContentfulPaint</a>
