# BackgroundFetchRecord.request

The `request` read-only property of the [`BackgroundFetchRecord`](../backgroundfetchrecord) interface returns the details of the resource to be fetched.

## Syntax

    var request = BackgroundFetchRecord.request;

### Value

A [`Request`](../request).

## Examples

In this example an individual `BackgroundFetchRecord` is returned using [`BackgroundFetchManager.fetch()`](../backgroundfetchmanager/fetch). The `request` is returned and logged to the console.

    bgFetch.match('/ep-5.mp3').then(async (record) => {
      if (!record) {
        console.log('No record found');
        return;
      }

      console.log(`Here's the request`, record.request);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#dom-backgroundfetchrecord-request">Background Fetch<br />
<span class="small">The definition of 'BackgroundFetchRecord.request' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`request`

74

79

No

No

62

No

No

74

No

53

No

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRecord/request" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRecord/request</a>
