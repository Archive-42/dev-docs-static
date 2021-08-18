ErrorEvent
==========

The `ErrorEvent` interface represents events providing information related to errors in scripts or in files.

Properties
----------

*Also inherits properties from its parent [`Event`](event)*.

 <span class="page-not-created">`ErrorEvent.message`</span> <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) containing a human-readable error message describing the problem.

 <span class="page-not-created">`ErrorEvent.filename`</span> <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) containing the name of the script file in which the error occurred.

 <span class="page-not-created">`ErrorEvent.lineno`</span> <span class="badge inline readonly">Read only </span>   
Is an `integer` containing the line number of the script file on which the error occurred.

 <span class="page-not-created">`ErrorEvent.colno`</span> <span class="badge inline readonly">Read only </span>   
Is an `integer` containing the column number of the script file on which the error occurred.

 <span class="page-not-created">`ErrorEvent.error`</span> <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Is a JavaScript `Object` that is concerned by the event.

Constructor
-----------

<span class="page-not-created">`ErrorEvent()`</span>  
Creates an `ErrorEvent` event with the given parameters.

Methods
-------

*Inherits methods from its parent [`Event`](event)*.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#the-errorevent-interface">HTML Living Standard<br />
<span class="small">The definition of 'ErrorEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added the <code>error</code> property and the 5th parameter to the constructor.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/webappapis.html#the-errorevent-interface">HTML5<br />
<span class="small">The definition of 'ErrorEvent' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ErrorEvent`

10

12

Yes

Yes

11

Yes

≤37

18

Yes

11

Yes

1.0

`ErrorEvent`

Yes

14

?

?

Yes

Yes

Yes

Yes

?

Yes

Yes

Yes

`colno`

Yes

12

Yes

?

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`error`

Yes

12

Yes

?

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`filename`

10

12

Yes

?

11

Yes

≤37

18

Yes

11

Yes

1.0

`lineno`

10

12

Yes

?

11

Yes

≤37

18

Yes

11

Yes

1.0

`message`

10

12

Yes

?

11

Yes

≤37

18

Yes

11

Yes

1.0

See also
--------

-   [Using web workers](web_workers_api/using_web_workers), most likely objects to raise such an event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ErrorEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ErrorEvent</a>
