MediaError
==========

The `MediaError` interface represents an error which occurred while handling media in an HTML media element based on [`HTMLMediaElement`](htmlmediaelement), such as [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video).

A `MediaError` object describes the error in general terms using a numeric `code` categorizing the kind of error, and a `message`, which provides specific diagnostics about what went wrong.

Properties
----------

*This interface doesn't inherit any properties.*

[`MediaError.code`](mediaerror/code)  
A number which represents the general type of error that occurred, as follows:

<table><thead><tr class="header"><th>Name</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>MEDIA_ERR_ABORTED</code></td><td><code>1</code></td><td>The fetching of the associated resource was aborted by the user's request.</td></tr><tr class="even"><td><code>MEDIA_ERR_NETWORK</code></td><td><code>2</code></td><td>Some kind of network error occurred which prevented the media from being successfully fetched, despite having previously been available.</td></tr><tr class="odd"><td><code>MEDIA_ERR_DECODE</code></td><td><code>3</code></td><td>Despite having previously been determined to be usable, an error occurred while trying to decode the media resource, resulting in an error.</td></tr><tr class="even"><td><code>MEDIA_ERR_SRC_NOT_SUPPORTED</code></td><td><code>4</code></td><td>The associated resource or media provider object (such as a <a href="mediastream"><code>MediaStream</code></a>) has been found to be unsuitable.</td></tr></tbody></table>

[`MediaError.message`](mediaerror/message)  
A [`DOMString`](domstring) object containing a human-readable string which provides *specific diagnostic information* to help the reader understand the error condition which occurred; specifically, it isn't a summary of what the error code means, but actual diagnostic information to help in understanding what exactly went wrong. This text and its format is not defined by the specification and will vary from one [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) to another. If no diagnostics are available, or no explanation can be provided, this value is an empty string (`""`).

Methods
-------

*This interface doesn't implement or inherit any methods, and has none of its own.*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#mediaerror">HTML Living Standard<br />
<span class="small">The definition of 'MediaError' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`MediaError`

1

12

4

3.5-4

9

≤12.1

3.1

1

18

4

≤12.1

2

1.0

`code`

Yes

12

3.5

9

Yes

10

Yes

Yes

4

Yes

10

Yes

`message`

59

79

52

No

46

No

59

59

52

43

No

7.0

See also
--------

-   [`HTMLMediaElement.error`](htmlmediaelement/error)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaError" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaError</a>
