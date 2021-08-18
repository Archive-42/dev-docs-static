# ProgressEvent

The `ProgressEvent` interface represents events measuring progress of an underlying process, like an HTTP request (for an `XMLHttpRequest`, or the loading of the underlying resource of an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img), [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio), [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video), [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) or [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link)).

## Constructor

[`ProgressEvent()`](progressevent/progressevent)  
Creates a `ProgressEvent` event with the given parameters.

## Properties

_Also inherits properties from its parent [`Event`](event)_.

[`ProgressEvent.lengthComputable`](progressevent/lengthcomputable) <span class="badge inline readonly">Read only </span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating if the total work to be done, and the amount of work already done, by the underlying process is calculable. In other words, it tells if the progress is measurable or not.

[`ProgressEvent.loaded`](progressevent/loaded) <span class="badge inline readonly">Read only </span>  
A 64-bit unsigned integer value indicating the amount of work already performed by the underlying process. The ratio of work done can be calculated by dividing `total` by the value of this property. When downloading a resource using HTTP, this only counts the body of the HTTP message, and doesn't include headers and other overhead.

[`ProgressEvent.total`](progressevent/total) <span class="badge inline readonly">Read only </span>  
A 64-bit unsigned integer representing the total amount of work that the underlying process is in the progress of performing. When downloading a resource using HTTP, this is the `Content-Length` (the size of the body of the message), and doesn't include the headers and other overhead.

## Methods

_Also inherits methods from its parent [`Event`](event)._

[`ProgressEvent.initProgressEvent()`](progressevent/initprogressevent) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span><span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Initializes a `ProgressEvent` created using the deprecated [`Document.createEvent("ProgressEvent")`](document/createevent) method.

## Examples

The following example adds a `ProgressEvent` to a new [`XMLHTTPRequest`](xmlhttprequest) and uses it to display the status of the request.

    var progressBar = document.getElementById("p"),
        client = new XMLHttpRequest()
    client.open("GET", "magical-unicorns")
    client.onprogress = function(pe) {
      if(pe.lengthComputable) {
        progressBar.max = pe.total
        progressBar.value = pe.loaded
      }
    }
    client.onloadend = function(pe) {
      progressBar.value = pe.loaded
    }
    client.send()

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#interface-progressevent">XMLHttpRequest<br />
<span class="small">The definition of 'ProgressEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`ProgressEvent`

1

12

3.5

10

Yes

Yes

≤37

Yes

4

Yes

Yes

Yes

`ProgressEvent`

Yes

≤79

22

No

Yes

Yes

Yes

Yes

22

Yes

Yes

Yes

`initProgressEvent`

1-17

12-79

3.5-22

10

Yes-15

Yes-6

No

Yes-18

4-22

Yes-14

Yes-6

No

`lengthComputable`

50

12

3.5

Yes

37

3.1

50

50

4

37

2

5.0

`loaded`

Yes

12

3.5

No

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`total`

Yes

12

3.5

No

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

## See also

- The [`Event`](event) base interface.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ProgressEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ProgressEvent</a>
