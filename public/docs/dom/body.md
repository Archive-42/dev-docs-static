# Body

The `Body` [mixin](https://developer.mozilla.org/en-US/docs/Glossary/Mixin) of the [Fetch API](fetch_api) represents the body of the response/request, allowing you to declare what its content type is and how it should be handled.

`Body` is implemented by both [`Request`](request) and [`Response`](response). This provides these objects with an associated body (a [stream](streams_api)), a used flag (initially unset), and a MIME type (initially the empty byte sequence).

## Properties

[`Body.body`](body/body) <span class="badge inline readonly">Read only </span>  
A simple getter used to expose a [`ReadableStream`](readablestream) of the body contents.

[`Body.bodyUsed`](body/bodyused) <span class="badge inline readonly">Read only </span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether the body has been read.

## Methods

[`Body.arrayBuffer()`](body/arraybuffer)  
Takes a [`Response`](response) stream and reads it to completion. It returns a promise that resolves with an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer).

[`Body.blob()`](body/blob)  
Takes a [`Response`](response) stream and reads it to completion. It returns a promise that resolves with a [`Blob`](blob).

[`Body.formData()`](body/formdata)  
Takes a [`Response`](response) stream and reads it to completion. It returns a promise that resolves with a [`FormData`](formdata) object.

[`Body.json()`](body/json)  
Takes a [`Response`](response) stream and reads it to completion. It returns a promise that resolves with the result of parsing the body text as [`JSON`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON).

[`Body.text()`](body/text)  
Takes a [`Response`](response) stream and reads it to completion. It returns a promise that resolves with a [`USVString`](usvstring) (text). The response is _always_ decoded using UTF-8.

## Examples

The example below uses a simple fetch call to grab an image and display it in an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) tag. You'll notice that since we are requesting an image, we need to run [`Body.blob()`](body/blob) ([`Response`](response) implements body) to give the response its correct MIME type.

### HTML Content

    <img class="my-image" src="https://wikipedia.org/static/images/project-logos/frwiki-1.5x.png">

### JS Content

    const myImage = document.querySelector('.my-image');
    fetch('https://upload.wikimedia.org/wikipedia/commons/7/77/Delete_key1.jpg')
        .then(res => res.blob())
        .then(res => {
            const objectURL = URL.createObjectURL(res);
            myImage.src = objectURL;
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#body-mixin">Fetch<br />
<span class="small">The definition of 'Body' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`Body`

42

≤18

39

No

29

10.1

42

42

?

29

10.3

4.0

`arrayBuffer`

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

`blob`

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

`body`

52

≤18

65

No

39

11.1

52

52

65

41

11.3

6.0

`bodyUsed`

42

≤18

39

No

29

10.1

No

No

No

29

10.3

No

`formData`

60

≤79

39

No

47

10.1

From Safari 10.1, the method exists but always rejects with `NotSupportedError`. See [bug 215671](https://webkit.org/b/215671).

60

60

No

44

10.3

From Safari for iOS 10.3, the method exists but always rejects with `NotSupportedError`. See [bug 215671](https://webkit.org/b/215671).

8.0

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

- [ServiceWorker API](service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Body" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Body</a>
