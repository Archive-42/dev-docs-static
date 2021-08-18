performance.toJSON()
====================

The `toJSON()` method of the [`Performance`](../performance) interface is a standard serializer: it returns a JSON representation of the performance object's properties.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    myPerf = performance.toJSON()

### Arguments

None

### Return value

myPerf  
A JSON object that is the serialization of the [`Performance`](../performance) object.

Example
-------

    var js;
    js = window.performance.toJSON();
    console.log("json = " + JSON.stringify(js));

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/hr-time-2/#dom-performance-tojson">High Resolution Time Level 2<br />
<span class="small">The definition of 'toJSON() serializer' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines <code>toJson()</code>.</td></tr></tbody></table>

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

`toJSON`

56

12

25

9

No

14.1

56

56

25

No

14.5

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Performance/toJSON" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Performance/toJSON</a>
