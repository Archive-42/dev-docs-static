# PerformanceResourceTiming

The `PerformanceResourceTiming` interface enables retrieval and analysis of detailed network timing data regarding the loading of an application's _resources_. An application can use the timing metrics to determine, for example, the length of time it takes to fetch a specific resource, such as an [`XMLHttpRequest`](xmlhttprequest), [`<SVG>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg), image, or script.

The interface's properties create a _resource loading timeline_ with [`high-resolution timestamps`](domhighrestimestamp) for network events such as redirect start and end times, fetch start, DNS lookup start and end times, response start and end times, etc.. Additionally, the interface extends [`PerformanceEntry`](performanceentry) with other properties which provide data about the size of the fetched resource as well as the _type_ of resource that initiated the fetch.

**Note:** This feature is available in [Web Workers](web_workers_api).

## Properties

This interface extends the following [`PerformanceEntry`](performanceentry) properties for resource performance entry types by qualifying and constraining them as follows:

[`PerformanceEntry.entryType`](performanceentry/entrytype)<span class="badge inline readonly">Read only </span>  
Returns `"resource"`.

[`PerformanceEntry.name`](performanceentry/name)<span class="badge inline readonly">Read only </span>  
Returns the resources URL.

[`PerformanceEntry.startTime`](performanceentry/starttime)<span class="badge inline readonly">Read only </span>  
Returns the [`timestamp`](domhighrestimestamp) for the time a resource fetch started. This value is equivalent to [`PerformanceResourceTiming.fetchStart`](performanceresourcetiming/fetchstart).

[`PerformanceEntry.duration`](performanceentry/duration)<span class="badge inline readonly">Read only </span>  
Returns a [`timestamp`](domhighrestimestamp) that is the difference between the [`responseEnd`](performanceresourcetiming/responseend) and the [`startTime`](performanceentry/starttime) properties.

The interface also supports the following properties which are listed in the order in which they are recorded for the fetching of a single resource. An alphabetical listing is shown in the navigation, at left.

[`PerformanceResourceTiming.initiatorType`](performanceresourcetiming/initiatortype)<span class="badge inline readonly">Read only </span>  
A [`string`](domstring) representing the _type_ of resource that initiated the performance entry, as specified in [`PerformanceResourceTiming.initiatorType`](performanceresourcetiming/initiatortype).

[`PerformanceResourceTiming.nextHopProtocol`](performanceresourcetiming/nexthopprotocol)<span class="badge inline readonly">Read only </span>  
A [`string`](domstring) representing the _network protocol_ used to fetch the resource, as identified by the [ALPN Protocol ID (RFC7301)](https://datatracker.ietf.org/doc/html/rfc7301).

[`PerformanceResourceTiming.workerStart`](performanceresourcetiming/workerstart)<span class="badge inline readonly">Read only </span>  
Returns a [`DOMHighResTimeStamp`](domhighrestimestamp) immediately before dispatching the [`FetchEvent`](fetchevent) if a Service Worker thread is already running, or immediately before starting the Service Worker thread if it is not already running. If the resource is not intercepted by a Service Worker the property will always return 0.

[`PerformanceResourceTiming.redirectStart`](performanceresourcetiming/redirectstart)<span class="badge inline readonly">Read only </span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) that represents the start time of the fetch which initiates the redirect.

[`PerformanceResourceTiming.redirectEnd`](performanceresourcetiming/redirectend)<span class="badge inline readonly">Read only </span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) immediately after receiving the last byte of the response of the last redirect.

[`PerformanceResourceTiming.fetchStart`](performanceresourcetiming/fetchstart)<span class="badge inline readonly">Read only </span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) immediately before the browser starts to fetch the resource.

[`PerformanceResourceTiming.domainLookupStart`](performanceresourcetiming/domainlookupstart)<span class="badge inline readonly">Read only </span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) immediately before the browser starts the domain name lookup for the resource.

[`PerformanceResourceTiming.domainLookupEnd`](performanceresourcetiming/domainlookupend)<span class="badge inline readonly">Read only </span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) representing the time immediately after the browser finishes the domain name lookup for the resource.

[`PerformanceResourceTiming.connectStart`](performanceresourcetiming/connectstart)<span class="badge inline readonly">Read only </span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) immediately before the browser starts to establish the connection to the server to retrieve the resource.

[`PerformanceResourceTiming.connectEnd`](performanceresourcetiming/connectend)<span class="badge inline readonly">Read only </span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) immediately after the browser finishes establishing the connection to the server to retrieve the resource.

[`PerformanceResourceTiming.secureConnectionStart`](performanceresourcetiming/secureconnectionstart)<span class="badge inline readonly">Read only </span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) immediately before the browser starts the handshake process to secure the current connection.

[`PerformanceResourceTiming.requestStart`](performanceresourcetiming/requeststart)<span class="badge inline readonly">Read only </span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) immediately before the browser starts requesting the resource from the server.

[`PerformanceResourceTiming.responseStart`](performanceresourcetiming/responsestart)<span class="badge inline readonly">Read only </span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) immediately after the browser receives the first byte of the response from the server.

[`PerformanceResourceTiming.responseEnd`](performanceresourcetiming/responseend)<span class="badge inline readonly">Read only </span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) immediately after the browser receives the last byte of the resource or immediately before the transport connection is closed, whichever comes first.

[`PerformanceResourceTiming.transferSize`](performanceresourcetiming/transfersize)<span class="badge inline readonly">Read only </span>  
A `number` representing the size (in octets) of the fetched resource. The size includes the response header fields plus the response payload body.

[`PerformanceResourceTiming.encodedBodySize`](performanceresourcetiming/encodedbodysize)<span class="badge inline readonly">Read only </span>  
A `number` representing the size (in octets) received from the fetch (HTTP or cache), of the _payload body_, before removing any applied content-codings.

[`PerformanceResourceTiming.decodedBodySize`](performanceresourcetiming/decodedbodysize)<span class="badge inline readonly">Read only </span>  
A `number` that is the size (in octets) received from the fetch (HTTP or cache) of the _message body_, after removing any applied content-codings.

[`PerformanceResourceTiming.serverTiming`](performanceresourcetiming/servertiming)<span class="badge inline readonly">Read only </span>  
An array of [`PerformanceServerTiming`](performanceservertiming) entries containing server timing metrics.

## Methods

[`PerformanceResourceTiming.toJSON()`](performanceresourcetiming/tojson)  
Returns a [`DOMString`](domstring) that is the JSON representation of the [`PerformanceResourceTiming`](performanceresourcetiming) object.

## Example

See the example in [Using the Resource Timing API](resource_timing_api/using_the_resource_timing_api).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/resource-timing-1/#performanceresourcetiming">Resource Timing Level 1<br />
<span class="small">The definition of 'PerformanceResourceTiming' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PerformanceResourceTiming`

43

12

40

10

30

11

43

43

42

30

11

4.0

`connectEnd`

43

12

40

10

32

11

43

43

42

32

11

4.0

`connectStart`

43

12

40

10

32

11

43

43

42

32

11

4.0

`decodedBodySize`

54

17

45

No

41

No

54

54

45

41

No

6.0

`domainLookupEnd`

43

12

40

No

30

11

43

43

42

30

11

4.0

`domainLookupStart`

43

12

40

No

30

11

43

43

42

30

11

4.0

`encodedBodySize`

54

17

45

No

41

No

54

54

45

41

No

6.0

`fetchStart`

43

12

40

No

30

11

43

43

42

30

11

4.0

`initiatorType`

43

12

40

No

30

11

43

43

42

30

11

4.0

`nextHopProtocol`

61

17

45

No

No

No

61

61

45

No

No

8.0

`redirectEnd`

43

12

40

No

30

11

43

43

42

30

11

4.0

`redirectStart`

43

12

40

No

30

11

43

43

42

30

11

4.0

`requestStart`

43

12

40

No

30

11

43

43

42

30

11

4.0

`responseEnd`

43

12

40

No

30

11

43

43

42

30

11

4.0

`responseStart`

43

12

40

No

30

11

43

43

42

30

11

4.0

`secureConnectionStart`

43

18

40

No

30

11

43

43

42

30

11

4.0

`serverTiming`

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

43

≤18

40

No

30

11

43

43

42

30

11

4.0

`transferSize`

54

17

45

No

41

No

54

54

45

41

No

6.0

`worker_support`

43

≤18

60

No

32

12

43

43

60

32

No

4.0

`workerStart`

43

16

58

No

32

11

43

43

58

32

11

4.0

## See also

- [Resource Timing (Overview)](resource_timing_api)
- [Using the Resource Timing API](resource_timing_api/using_the_resource_timing_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceResourceTiming</a>
