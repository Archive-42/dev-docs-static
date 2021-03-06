USBEndpoint
===========

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `USBEndpoint` interface of the [WebUSB API](webusb_api) provides information about an endpoint provided by the USB device. An endpoint represents a unidirectional data stream into or out of a device.

Constructor
-----------

`USBEndpoint.USBEndpoint`  
Creates a new `USBEndpoint` object which will be populated with information about the endpoint on the provided <span class="page-not-created">`USBAltenateInterface`</span> with the given endpoint number and transfer direction.

Properties
----------

`USBEndpoint.endpointNumber`  
Returns this endpoint's "endpoint number" which is a value from 1 to 15 extracted from the `bEndpointAddress` field of the endpoint descriptor defining this endpoint. This value is used to identify the endpoint when calling methods on `USBDevice`.

`USBEndpoint.direction`  
Returns the direction in which this endpoint transfers data, one of:

-   `"in"` - Data is transferred from device to host.

-   `"out"` - Data is transferred from host to device.

`USBEndpoint.type`  
Returns the type of this endpoint, one of:

-   `"bulk"` - Provides reliable data transfer for large payloads. Data sent through a bulk endpoint is guaranteed to be delivered or generate an error but may be preempted by other data traffic.

-   `"interrupt"` - Provides reliable data transfer for small payloads. Data sent through an interrupt endpoint is guaranteed to be delivered or generate an error and is also given dedicated bus time for transmission.

-   `"isochronous"` - Provides unreliable data transfer for payloads that must be delivered periodically. They are given dedicated bus time but if a deadline is missed the data is dropped.

<!-- -->

`USBEndpoint.packetSize`  
Returns the size of the packets that data sent through this endpoint will be divided into.

Examples
--------

While sometimes the developer knows ahead of time the exact layout of a device's endpoints there are cases where this must be discovered at runtime. For example, a USB serial device must provide bulk input and output endpoints but their endpoint numbers will depend on what other interfaces the device provides.

This code identifies the correct endpoints by searching for the interface implementing the USB CDC interface class and then identifying the candidate endpoints based on their type and direction.

    let inEndpoint = undefined;
    let outEndpoint = undefined;

    for (const interface of device.configuration.interfaces) {
      // Only support devices with out multiple alternate interfaces.
      const alternate = interface.alternates[0];

      // Identify the interface implementing the USB CDC class.
      const USB_CDC_CLASS = 10;
      if (alternate.interfaceClass != USB_CDC_CLASS) {
        continue;
      }

      for (const endpoint of alternate.endpoints) {
        // Identify the bulk transfer endpoints.
        if (endpoint.type != "bulk") {
          continue;
        }

        if (endpoint.direction == "in") {
          inEndpoint = endpoint.endpointNumber;
        } else if (endpoint.direction == "out") {
          outEndpoint = endpoint.endpointNumber;
        }
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/webusb/#endpoints">WebUSB<br />
<span class="small">The definition of 'USBEndPoint' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`USBEndpoint`

61

79

No

No

48

No

No

61

No

45

No

8.0

`USBEndpoint`

61

79

No

No

48

No

No

61

No

45

No

8.0

`direction`

61

79

No

No

48

No

No

61

No

45

No

8.0

`endpointNumber`

61

79

No

No

48

No

No

61

No

45

No

8.0

`packetSize`

61

79

No

No

48

No

No

61

No

45

No

8.0

`type`

61

79

No

No

48

No

No

61

No

45

No

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USBEndpoint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USBEndpoint</a>
