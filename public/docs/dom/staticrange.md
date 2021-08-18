StaticRange
===========

The [DOM](document_object_model) `StaticRange` interface extends [`AbstractRange`](abstractrange) to provide a method to specify a range of content in the DOM whose contents don't update to reflect changes which occur within the DOM tree. It offers the same set of properties and methods as `AbstractRange`.

`AbstractRange` and `StaticRange` are not available from [web workers](web_workers_api).

Constructor
-----------

[`StaticRange()`](staticrange/staticrange)  
Creates a new `StaticRange` object given the <span class="page-not-created">`StaticRangeInit`</span> dictionary specifying the default values for its properties.

Properties
----------

*The properties below are inherited from its parent interface, [`AbstractRange`](abstractrange).*

 [`StaticRange.collapsed`](staticrange/collapsed) <span class="badge inline readonly">Read only </span>   
Returns a Boolean value which is `true` if the range's start and end positions are the same, resulting in a range of length 0.

 [`StaticRange.endContainer`](staticrange/endcontainer) <span class="badge inline readonly">Read only </span>   
Returns the DOM [`Node`](node) which contains the ending point of the range. The offset into the node at which the end position is located is indicated by `endOffset`.

 [`StaticRange.endOffset`](staticrange/endoffset) <span class="badge inline readonly">Read only </span>   
Returns an integer value indicating the offset into the node given by `endContainer` at which the last character of the range is found.

 [`StaticRange.startContainer`](staticrange/startcontainer) <span class="badge inline readonly">Read only </span>   
Returns the DOM [`Node`](node) which contains the starting point of the range (which is in turn identified by `startOffset`.

 [`StaticRange.startOffset`](staticrange/startoffset) <span class="badge inline readonly">Read only </span>   
Returns an integer value indicating the offset into the node specified by `startContainer` at which the first character of the range is located.

Methods
-------

<span class="page-not-created">`StaticRange.toRange()`</span>  
Returns a new [`Range`](range) object which describes the same range as the source `StaticRange`, but is "live" with values that change to reflect changes in the contents of the DOM tree.

Usage notes
-----------

A DOM range specifies a span of content in a document, potentially beginning inside one node (or element) and ending inside another one. Unlike a [`Range`](range), a `StaticRange` represents a range which is fixed in time; it does not change to try to keep the same content within it as the document changes. If any changes are made to the DOM, the actual data contained within the range specified by a `StaticRange` may change. This lets the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) avoid a lot of work that is unnecessary if the web app or site doesn't need a live-updating range.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-staticrange">DOM<br />
<span class="small">The definition of 'StaticRange' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://w3c.github.io/staticrange/#interface-staticrange">Static Range<br />
<span class="small">The definition of 'StaticRange' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`StaticRange`

60

18

69

In Firefox, `StaticRange` can currently only be used by browser-internal code or code with enhanced permissions; it is not yet exposed to the web.

No

47

10.1

60

60

No

44

10.3

8.0

`StaticRange`

No

No

71

No

No

13.1

No

No

No

No

13.4

No

`collapsed`

60

18

69

No

47

10.1

60

60

No

44

10.3

8.0

`endContainer`

60

18

69

No

47

10.1

60

60

No

44

10.3

8.0

`endOffset`

60

18

69

No

47

10.1

60

60

No

44

10.3

8.0

`startContainer`

60

18

69

No

47

10.1

60

60

No

44

10.3

8.0

`startOffset`

60

18

69

No

47

10.1

60

60

No

44

10.3

8.0

`toRange`

60

18

No

No

47

No

60

60

No

44

No

8.0

See also
--------

-   Live updating range of content within the DOM: [`Range`](range)
-   [`AbstractRange`](abstractrange), the abstract interface from which all ranges are derived

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StaticRange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StaticRange</a>
