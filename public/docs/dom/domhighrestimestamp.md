# DOMHighResTimeStamp

The `DOMHighResTimeStamp` type is a `double` and is used to store a time value in milliseconds. This type can be used to describe a discrete point in time or a time interval (the difference in time between two discrete points in time).

The time, given in milliseconds, should be accurate to 5 µs (microseconds), with the fractional part of the number indicating fractions of a millisecond. However, if the browser is unable to provide a time value accurate to 5 µs (due, for example, to hardware or software constraints), the browser can represent the value as a time in milliseconds accurate to a millisecond. Also note the section below on reduced time precision controlled by browser preferences to avoid timing attacks and fingerprinting.

Further, if the device or operating system the user agent is running on doesn't have a clock accurate to the microsecond level, they may only be accurate to the millisecond.

## Reduced time precision

To offer protection against timing attacks and fingerprinting, the precision of time stamps might get rounded depending on browser settings. In Firefox, the `privacy.reduceTimerPrecision` preference is enabled by default and defaults to 20 µs in Firefox 59; in 60 it will be 2ms.

    // reduced time precision (2ms) in Firefox 60
    event.timeStamp
    // 1519211809934
    // 1519211810362
    // 1519211811670
    // ...

    // reduced time precision with `privacy.resistFingerprinting` enabled
    event.timeStamp;
    // 1519129853500
    // 1519129858900
    // 1519129864400
    // ...

In Firefox, you can also enable `privacy.resistFingerprinting`, the precision will be 100ms or the value of `privacy.resistFingerprinting.reduceTimerPrecision.microseconds`, whichever is larger.

## Properties

_This type has no properties. It is a double-precision floating-point value._

### Value

The value of a `DOMHighResTimeStamp` is a double-precision floating-point number which describes the number of milliseconds (accurate to within 5 microseconds if the device supports it) elapsed between two points in time. The starting time can be either a specific time determined by the script for a site or app, or the **time origin**.

#### The time origin

The **time origin** is a standard time which is considered to be the beginning of the current document's lifetime. It's calculated like this:

- If the script's [global object](https://developer.mozilla.org/en-US/docs/Glossary/Global_object) is a [`Window`](window), the time origin is determined as follows:
  - If the current [`Document`](document) is the first one loaded in the `Window`, the time origin is the time at which the browser context was created.
  - If during the process of unloading the previous document which was loaded in the window, a confirmation dialog was displayed to let the user confirm whether or not to leave the previous page, the time origin is the time at which the user confirmed that navigating to the new page was acceptable.
  - If neither of the above determines the time origin, then the time origin is the time at which the navigation responsible for creating the window's current `Document` took place.
- If the script's global object is a [`WorkerGlobalScope`](workerglobalscope) (that is, the script is running as a web worker), the time origin is the moment at which the worker was created.
- In all other cases, the time origin is undefined.

## Methods

_This type has no methods._

## Usage notes

You can get the current timestamp value—the time that has elapsed since the context was created—by calling the [`performance`](performance) method [`now()`](performance/now). This method is available in both [`Window`](window) and [`Worker`](worker) contexts.

## Example

To determine how much time has elapsed since a particular point in your code, you can do something like this:

    let startTime = performance.now();

    /* ... do things for a while ... */

    let elapsedTime = performance.now() - startTime;

Upon completion, the value of `elapsedTime` is the number of milliseconds that have elapsed since you recorded the starting time in line 1.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/hr-time-2/#dom-domhighrestimestamp">High Resolution Time Level 2<br />
<span class="small">The definition of 'DOMHighResTimeStamp' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Stricter definitions of interfaces and types.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/hr-time-1/#sec-DOMHighResTimeStamp">High Resolution Time<br />
<span class="small">The definition of 'DOMHighResTimeStamp' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.DOMHighResTimestamp`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [Navigation Timing API](navigation_timing_api)
- [`Performance`](performance)
- `performance.now()`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMHighResTimeStamp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMHighResTimeStamp</a>
