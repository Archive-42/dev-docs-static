# Body.json()

The `json()` method of the [`Body`](../body) mixin takes a [`Response`](../response) stream and reads it to completion. It returns a promise which resolves with a JavaScript object that is the result of parsing the body text as [`JSON`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON).

Note that despite the method being named `json()`, the result is not JSON but is instead the result of taking JSON as input and parsing it to produce a JavaScript object.

## Syntax

    response.json().then(data => {
      // do something with your data
    });

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a JavaScript object. This object could be anything that can be represented by JSON — an object, an array, a string, a number...

## Example

In our [fetch json example](https://github.com/mdn/fetch-examples/tree/master/fetch-json) (run [fetch json live](https://mdn.github.io/fetch-examples/fetch-json/)), we create a new request using the [`Request()`](../request/request) constructor, then use it to fetch a `.json` file. When the fetch is successful, we read and parse the data using `json()`, then read values out of the resulting objects as you'd expect and insert them into list items to display our product data.

    const myList = document.querySelector('ul');
    const myRequest = new Request('products.json');

    fetch(myRequest)
      .then(response => response.json())
      .then(data => {
        for (const product of data.products) {
          let listItem = document.createElement('li');
          listItem.appendChild(
            document.createElement('strong')
          ).textContent = product.Name;
          listItem.append(
            ` can be found in ${
              product.Location
            }. Cost: `
          );
          listItem.appendChild(
            document.createElement('strong')
          ).textContent = `£${product.Price}`;
          myList.appendChild(listItem);
        }
      })
      .catch(console.error);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-body-json">Fetch<br />
<span class="small">The definition of 'Body.json()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`json`

42

≤18

39

No

29

10.1

No

42

No

29

10.3

4.0

## See also

- [ServiceWorker API](../service_worker_api)
- [Cross-Origin Resource Sharing (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Body/json" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Body/json</a>
