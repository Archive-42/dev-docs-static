# Body.body

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `body` read-only property of the [`Body`](../body) mixin is a simple getter used to expose a [`ReadableStream`](../readablestream) of the body contents.

## Syntax

    var stream = response.body;

### Value

A [`ReadableStream`](../readablestream).

## Example

In our [simple stream pump](https://mdn.github.io/dom-examples/streams/simple-pump/) example we fetch an image, expose the response's stream using `response.body`, create a reader using [`ReadableStream.getReader()`](../readablestream/getreader), then enqueue that stream's chunks into a second, custom readable stream — effectively creating an identical copy of the image.

    const image = document.getElementById('target');

    // Fetch the original image
    fetch('./tortoise.png')
    // Retrieve its body as ReadableStream
    .then(response => response.body)
    .then(body => {
      const reader = body.getReader();

      return new ReadableStream({
        start(controller) {
          return pump();

          function pump() {
            return reader.read().then(({ done, value }) => {
              // When no more data needs to be consumed, close the stream
              if (done) {
                controller.close();
                return;
              }

              // Enqueue the next data chunk into our target stream
              controller.enqueue(value);
              return pump();
            });
          }
        }
      })
    })
    .then(stream => new Response(stream))
    .then(response => response.blob())
    .then(blob => URL.createObjectURL(blob))
    .then(url => console.log(image.src = url))
    .catch(err => console.error(err));

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-body-body">Fetch<br />
<span class="small">The definition of 'body' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

## See also

- [Fetch API](../fetch_api)
- [Streams API](../streams_api)
- [ServiceWorker API](../service_worker_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Body/body" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Body/body</a>
