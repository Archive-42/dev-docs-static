Presentation.receiver
=====================

The **read-only** [`Presentation`](../presentation) attribute `receiver`, which is only available in browser contexts which are **receiving** a presentation, returns the [`PresentationReceiver`](../presentationreceiver) object which can be used to access and communicate with the browser context which controls the presentation. This property is always `null` when accessed from outside a browser context which is receiving a presentation.

Syntax
------

    receiver = Presentation.receiver;

    receiver = navigator.presentation.receiver;

Since the [`Presentation`](../presentation) interface is typically accessed through <span class="page-not-created">`navigation.presentation`</span>, the second form of the syntax shown above is the more commonly used.

### Value

If the code is running in a context which is receiving a presentation, the returned value is a [`PresentationReceiver`](../presentationreceiver) which can then be used to communicate with the context which is the source of the presentation.

If the current context is not receiving a presentation, `receiver` is `null`.

Example
-------

### Determining whether or not the context is receiving a presentation

You can easily determine whether or not the context is the receiver for a presentation by checking the value of `navigator.receiver`. If it's a non-null value, then the context is indeed receiving a presentation. If it's `null`, there's no incoming presentation.

    if (navigator.receiver) {
      footer.innerHTML = "Receiving presentation";
    }  else {
      footer.innerHTML = "(idle)";
    }

### Accessing the connection list

This example uses `receiver` to access the list of incoming connections and to build and display a list of those connections' ID strings.

    let listElem = document.getElementById("connectionview");

    navigator.presentation.receiver.connectionList
              .then(function(connections) {
        connections.forEach(function(aConnection)) {
          listElem.innerHTML += "<li>" + aConnection.id
                + "</li>";
        });
    });

After getting access to the output list element in the variable `connectionView`, <span class="page-not-created">`navigator.receiver`</span> is used to get a reference to the [`PresentationReceiver`](../presentationreceiver) object for this context, and its <span class="page-not-created">`connectionList`</span> is used to get a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which will be called when the list is available.

The promise handler receives as its input parameter an array of the incoming connections. We iterate over these using [`forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach), appending a new item to the `connectionView` list element for each connection.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/presentation-api/#dom-presentation-receiver">Presentation API<br />
<span class="small">The definition of 'receiver' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`receiver`

48

≤79

51-88

No

Yes

No

No

48

51-79

Yes

No

5.0

See also
--------

-   Presentation API
-   [`Presentation`](../presentation)
-   [`PresentationReceiver`](../presentationreceiver)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Presentation/receiver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Presentation/receiver</a>
