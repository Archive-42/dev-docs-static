# Body.text()

The `text()` method of the [`Body`](../body) mixin takes a [`Response`](../response) stream and reads it to completion. It returns a promise that resolves with a [`USVString`](../usvstring) object (text). The response is _always_ decoded using UTF-8.

## Syntax

    response.text().then(function (text) {
      // do something with the text response
    });

### Parameters

None.

### Return value

A Promise that resolves with a [`USVString`](../usvstring).

## Example

In our [fetch text example](https://github.com/mdn/fetch-examples/tree/master/fetch-text) (run [fetch text live](https://mdn.github.io/fetch-examples/fetch-text/)), we have an [`<article>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article) element and three links (stored in the `myLinks` array.) First, we loop through all of these and give each one an `onclick` event handler so that the `getData()` function is run — with the link's `data-page` identifier passed to it as an argument — when one of the links is clicked.

When `getData()` is run, we create a new request using the [`Request()`](../request/request) constructor, then use it to fetch a specific `.txt` file. When the fetch is successful, we read a [`USVString`](../usvstring) (text) object out of the response using `text()`, then set the [`innerHTML`](../element/innerhtml) of the [`<article>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article) element equal to the text object.

    let myArticle = document.querySelector('article');
    let myLinks = document.querySelectorAll('ul a');

    for(let i = 0; i <= myLinks.length-1; i++) {
      myLinks[i].onclick = function(e) {
        e.preventDefault();
        let linkData = e.target.getAttribute('data-page');
        getData(linkData);
      }
    };

    function getData(pageId) {
      console.log(pageId);
      var myRequest = new Request(pageId + '.txt');
      fetch(myRequest).then(function(response) {
        return response.text().then(function(text) {
          myArticle.innerHTML = text;
        });
      });
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-body-text">Fetch<br />
<span class="small">The definition of 'text()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`text`

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
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Body/text" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Body/text</a>
