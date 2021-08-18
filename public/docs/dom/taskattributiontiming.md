TaskAttributionTiming
=====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `TaskAttributionTiming` interface of the [Long Tasks API](long_tasks_api) returns information about the work involved in a long task and its associate frame context. The frame context, also called the container, is the iframe, embed or object that is being implicated, on the whole, for a long task.

Properties
----------

 [`TaskAttributionTiming.containerType`](taskattributiontiming/containertype) <span class="badge inline readonly">Read only </span>   
Returns the type of frame container, one of `iframe`, `embed`, or `object`.

 [`TaskAttributionTiming.containerSrc`](taskattributiontiming/containersrc) <span class="badge inline readonly">Read only </span>   
Returns the container's `src` attribute.

 [`TaskAttributionTiming.containerId`](taskattributiontiming/containerid) <span class="badge inline readonly">Read only </span>   
Returns the container's `id` attribute.

 [`TaskAttributionTiming.containerName`](taskattributiontiming/containername) <span class="badge inline readonly">Read only </span>   
Returns the container's `name` attribute.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/longtasks/#sec-TaskAttributionTiming">Long Tasks API 1<br />
<span class="small">The definition of 'TaskAttributionTiming' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`TaskAttributionTiming`

58

≤79

No

See [bug 1348405](https://bugzil.la/1348405).

No

Yes

No

58

58

No

See [bug 1348405](https://bugzil.la/1348405).

Yes

No

7.0

`containerId`

58

≤79

No

No

Yes

No

58

58

No

Yes

No

7.0

`containerName`

58

≤79

No

No

Yes

No

58

58

No

Yes

No

7.0

`containerSrc`

58

≤79

No

No

Yes

No

58

58

No

Yes

No

7.0

`containerType`

58

≤79

No

No

Yes

No

58

58

No

Yes

No

7.0

`toJSON`

58

79

No

No

45

No

58

58

No

43

No

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TaskAttributionTiming" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TaskAttributionTiming</a>
