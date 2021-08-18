# Using light sensors

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Ambient Light Events** give a web application access to a device's ambient light sensor to detect changes in light intensity.

## <span style="line-height: 1.572;">How Does it Work?</span>

When the light sensor of the device detects a change in light intensity, the browser is notified of the change and fires a [`DeviceLightEvent`](../devicelightevent) event. The event gives information about the light intensity of the device's environment.

The [`DeviceLightEvent`](../devicelightevent) provides a value attribute with light intensity in _lux_ which is generally treated as shown below.

10 ~ 50 lux : Dim Environment

100 ~ 1000 lux : Normal

&gt; 10000 lux : Bright

It uses the [`addEventListener`](../eventtarget/addeventlistener) method of the [`window`](../window) object.

    window.addEventListener("devicelight", function (event) {

    // Read out the lux value

    var luminosity = event.value;

    alert(luminosity);

    });

## Example:

    window.addEventListener('devicelight', function(event) {

    var bodyBg= document.body.style;

    //event.value is the lux value returned by the sensor on the device
    if (event.value < 100) {

    alert('Hey, you! You are working in a dark environment');

    bodyBg.backgroundColor="lightgrey";

    } else {

    bodyBg.backgroundColor="#fff";

    }

    });

This example shows how the API can actually be used in the wild. If your app contains a lot of white in the UI, it is usually beneficial to the user to change the UI to a darker color in a darker environment. The code alerts the user that they are working in a dark environment and then changes the page's background to a darker color.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ambient-light/">Ambient Light Sensor<br />
<span class="small">The definition of 'Ambient Light Events' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification</td></tr></tbody></table>

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

`Using_light_sensors`

No

13-79

62

See [bug 1462308](https://bugzil.la/1462308).

22-61

Not supported for MacBook with Touch Bar and Windows 7 (see [bug 754199](https://bugzil.la/754199)).

No

No

No

No

No

62

See [bug 1462308](https://bugzil.la/1462308).

15-61

No

No

No

`value`

No

13-79

62

See [bug 1462308](https://bugzil.la/1462308).

22-61

Not supported for MacBook with Touch Bar and Windows 7 (see [bug 754199](https://bugzil.la/754199)).

No

No

No

No

No

62

See [bug 1462308](https://bugzil.la/1462308).

15-61

No

No

No

## References:

- [Ambient Light Events and JavaScript detection : Robert Nyman](https://hacks.mozilla.org/2013/04/ambient-light-events-and-javascript-detection/)
- [Using light events](../ambient_light_events)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DeviceLightEvent/Using_light_sensors" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DeviceLightEvent/Using_light_sensors</a>
