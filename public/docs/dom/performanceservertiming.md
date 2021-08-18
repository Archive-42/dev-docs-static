# PerformanceServerTiming

**Note:** This feature is available in [Web Workers](web_workers_api).

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PerformanceServerTiming` interface surfaces server metrics that are sent with the response in the [`Server-Timing`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Server-Timing) HTTP header.

This interface is restricted to the same origin, but you can use the [`Timing-Allow-Origin`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Timing-Allow-Origin) header to specify the domains that are allowed to access the server metrics. Note that this interface is only available in secure contexts (HTTPS) in some browsers.

## Properties

[`PerformanceServerTiming.description`](performanceservertiming/description)<span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) value of the server-specified metric description, or an empty string.

[`PerformanceServerTiming.duration`](performanceservertiming/duration)<span class="badge inline readonly">Read only </span>  
A double that contains the server-specified metric duration, or value `0.0`.

[`PerformanceServerTiming.name`](performanceservertiming/name)<span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) value of the server-specified metric name.

## Methods

[`PerformanceServerTiming.toJSON()`](performanceservertiming/tojson)  
Returns a [`DOMString`](domstring) that is the JSON representation of the `PerformanceServerTiming` object.

## Example

Given a server that sends the [`Server-Timing`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Server-Timing) header, for example a node.js server like this:

    const http = require('http');

    function requestHandler(request, response) {
      const headers = {
        'Server-Timing': `
          cache;desc="Cache Read";dur=23.2,
          db;dur=53,
          app;dur=47.2
        `.replace(/\n/g, '')
      };
      response.writeHead(200, headers);
      response.write('');
      return setTimeout(_ => {
       response.end();
     }, 1000)
    };

    http.createServer(requestHandler).listen(3000).on('error', console.error);

The `PerformanceServerTiming` entries are now observable from JavaScript via the [`PerformanceResourceTiming.serverTiming`](performanceresourcetiming/servertiming) property:

    let entries = performance.getEntriesByType('resource');
    console.log(entries[0].serverTiming);
    // 0: PerformanceServerTiming {name: "cache", duration: 23.2, description: "Cache Read"}
    // 1: PerformanceServerTiming {name: "db", duration: 53, description: ""}
    // 2: PerformanceServerTiming {name: "app", duration: 47.2, description: ""}

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/server-timing/#the-performanceservertiming-interface">Server Timing<br />
<span class="small">The definition of 'PerformanceServerTiming' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PerformanceServerTiming`

65

≤79

61

No

52

No

65

65

61

47

No

9.0

`description`

65

≤79

61

No

52

No

65

65

61

47

No

9.0

`duration`

65

≤79

61

No

52

No

65

65

61

47

No

9.0

`name`

65

≤79

61

No

52

No

65

65

61

47

No

9.0

`toJSON`

65

≤79

61

No

52

No

65

65

61

47

No

9.0

## See also

- [`Server-Timing`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Server-Timing)
- [`PerformanceResourceTiming.serverTiming`](performanceresourcetiming/servertiming)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceServerTiming" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceServerTiming</a>
