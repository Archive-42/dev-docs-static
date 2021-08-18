# BackgroundFetchRecord.responseReady

The `responseReady` read-only property of the [`BackgroundFetchRecord`](../backgroundfetchrecord) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`Response`](../response).

## Syntax

    var response = BackgroundFetchRecord.responseReady;

### Value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`Response`](../response).

## Examples

In this example an individual `BackgroundFetchRecord` is returned using [`BackgroundFetchManager.fetch()`](../backgroundfetchmanager/fetch). The value of `responseReady` is returned and logged to the console.

    bgFetch.match('/ep-5.mp3').then(async (record) => {
      if (!record) {
        console.log('No record found');
        return;
      }

      const response = await record.responseReady;
      console.log(`Here's the response`, response);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#dom-backgroundfetchrecord-responseready">Background Fetch<br />
<span class="small">The definition of 'BackgroundFetchRecord.responseReady' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`responseReady`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRecord/responseReady" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchRecord/responseReady</a>
