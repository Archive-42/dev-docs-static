# NetworkInformation.downlinkMax

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `NetworkInformation.downlinkMax` read-only property returns the maximum downlink speed, in megabits per second (Mbps), for the underlying connection technology.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var max = NetworkInformation.downlinkMax

### Return value

- an `unrestricted double` representing the maximum downlink speed, in megabits per second (Mb/s), for the underlying connection technology.

## Examples

The following example monitors the connection using the `change` event and logs changes as they occur.

    function logConnectionType() {
      var connectionType = 'not supported';
      var downlinkMax = 'not supported';

      if ('connection' in navigator) {
        connectionType = navigator.connection.effectiveType;

        if ('downlinkMax' in navigator.connection) {
          downlinkMax = navigator.connection.downlinkMax;
        }
      }

      console.log('Current connection type: ' + connectionType +
        ' (downlink max: ' + downlinkMax + ')');
    }

    logConnectionType();
    navigator.connection.addEventListener('change', logConnectionType);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/netinfo/#dom-networkinformation-downlinkmax">Network Information API<br />
<span class="small">The definition of 'downlinkMax' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`downlinkMax`

61

Only supported in Chrome OS

No

No

No

No

No

50

38

No

45

No

3.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation/downlinkMax" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation/downlinkMax</a>
