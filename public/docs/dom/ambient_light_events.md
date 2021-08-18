# Ambient Light Events

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Warning**

Ambient Light Events not supported by any current major browser, and should not be used.

The ambient light events are a handy way to make a web page or an application aware of any change in the light intensity. It allows them to react to such a change, for example by changing the color contrast of the User Interface (UI) or by changing the exposure necessary to take a picture.

**Note**

This API is _not available_ in [Web Workers](web_workers_api) (it is not exposed in the [worker global context](web_workers_api#worker_global_contexts_and_functions)).

## Light Events

When the light sensor of a device detects a change in the light level, it notifies the browser of that change. When the browser gets such a notification, it fires a [`DeviceLightEvent`](devicelightevent) event that provides information about the exact light intensity (in lux units).

This event can be captured at the `window` object level by using the [`addEventListener`](eventtarget/addeventlistener) method (using the `devicelight` event name) or by attaching an event handler to the `window.ondevicelight` property.

Once captured, the event object gives access to the light intensity expressed in [lux](https://en.wikipedia.org/wiki/Lux) through the `DeviceLightEvent.value` property.

## Example

    if ('ondevicelight' in window) {
      window.addEventListener('devicelight', function(event) {
        var body = document.querySelector('body');
        if (event.value < 50) {
          body.classList.add('darklight');
          body.classList.remove('brightlight');
        } else {
          body.classList.add('brightlight');
          body.classList.remove('darklight');
        }
      });
    } else {
      console.log('devicelight event not supported');
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ambient-light/">Ambient Light Sensor<br />
<span class="small">The definition of 'Ambient Light Events' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`Ambient_Light_Events`

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

## See also

- [`DeviceLightEvent`](devicelightevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Ambient_Light_Events" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Ambient_Light_Events</a>
