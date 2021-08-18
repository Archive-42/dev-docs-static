Server-sent events
==================

Traditionally, a web page has to send a request to the server to receive new data; that is, the page requests data from the server. With server-sent events, it's possible for a server to send new data to a web page at any time, by pushing messages to the web page. These incoming messages can be treated as *[Events](event) + data* inside the web page.

**Note:** This feature is available in [Web Workers](web_workers_api).

Firefox does not currently support the use of server-sent events in service workers (it does support them dedicated and shared workers). See [bug 1681218](https://bugzilla.mozilla.org/show_bug.cgi?id=1681218).

Concepts and usage
------------------

To learn how to use server-sent events, see our article [Using server-sent events](server-sent_events/using_server-sent_events).

Interfaces
----------

[`EventSource`](eventsource)  
Defines all the features that handle connecting to a server, receiving events/data, errors, closing a connection, etc.

Examples
--------

-   [Simple SSE demo using PHP](https://github.com/mdn/dom-examples/tree/master/server-sent-events)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#server-sent-events">HTML Living Standard<br />
<span class="small">The definition of 'Server-sent events' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

See also
--------

### Tools

-   [Mercure: a real-time communication protocol (publish-subscribe) built on top of SSE](https://mercure.rocks)
-   [EventSource polyfill for Node.js](https://github.com/EventSource/eventsource)
-   Remy Sharp’s [EventSource polyfill](https://github.com/remy/polyfills/blob/master/EventSource.js)
-   Yaffle’s [EventSource polyfill](https://github.com/Yaffle/EventSource)
-   Rick Waldron’s [jquery plugin](https://github.com/rwldrn/jquery.eventsource)
-   intercooler.js [declarative SSE support](https://intercoolerjs.org/docs.html#sse)

### Related Topics

-   [AJAX](https://developer.mozilla.org/en-US/docs/Web/Guide/AJAX)
-   [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
-   [WebSockets](websockets_api)

### Other resources

-   A [Twitter like application](https://hacks.mozilla.org/2011/06/a-wall-powered-by-eventsource-and-server-sent-events/) powered by server-sent events and [its code on Github](https://github.com/mozilla/webowonder-demos/tree/master/demos/friends%20timeline).
-   [HTML5 and Server-sent events](https://dsheiko.com/weblog/html5-and-server-sent-events)
-   [Server-sent events using Asp.Net](https://rajudasa.blogspot.in/2012/05/html5-server-sent-events-using-aspnet.html)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events</a>
