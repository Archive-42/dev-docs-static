# navigator.hardwareConcurrency

**Note:** This feature is available in [Web Workers](../web_workers_api).

The `navigator.hardwareConcurrency` read-only property returns the number of logical processors available to run threads on the user's computer.

## Syntax

    logicalProcessors = window.navigator.hardwareConcurrency

## Value

A [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) indicating the number of logical processor cores.

Modern computers have multiple physical processor cores in their CPU (two or four cores is typical), but each physical core is also usually able to run more than one thread at a time using advanced scheduling techniques. So a four-core CPU may offer eight **logical processor cores**, for example. The number of logical processor cores can be used to measure the number of threads which can effectively be run at once without them having to context switch.

The browser may, however, choose to report a lower number of logical cores in order to represent more accurately the number of [`Worker`](../worker)s that can run at once, so don't treat this as an absolute measurement of the number of cores in the user's system.

## Examples

In this example, one [`Worker`](../worker) is created for each logical processor reported by the browser and a record is created which includes a reference to the new worker as well as a Boolean value indicating whether or not we're using that worker yet; these objects are, in turn, stored into an array for later use. This creates a pool of workers we can use to process requests later.

    let workerList = [];

    for (let i = 0; i < window.navigator.hardwareConcurrency; i++) {
      let newWorker = {
        worker: new Worker('cpuworker.js'),
        inUse: false
      };
      workerList.push(newWorker);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-navigator-hardwareconcurrency">HTML Living Standard<br />
<span class="small">The definition of 'navigator.hardwareConcurrency' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`hardwareConcurrency`

37

15

48

No

24

10.1-11

37

37

48

24

10.3-11

3.0

## See also

- [`Navigator`](../navigator)
- [`WorkerNavigator`](../workernavigator)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NavigatorConcurrentHardware/hardwareConcurrency" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NavigatorConcurrentHardware/hardwareConcurrency</a>
