# console.trace()

The [`console`](../console) interface's `trace()` method outputs a stack trace to the [Web Console](https://developer.mozilla.org/en-US/docs/Tools/Web_Console).

**Note:** This feature is available in [Web Workers](../web_workers_api).

See [Stack traces](../console#stack_traces) in the [`console`](../console) documentation for details and examples.

## Syntax

    console.trace( [...any, ...data ]);

### Parameters

`...any, ...data` <span class="badge inline optional">Optional</span>  
Zero or more objects to be output to console along with the trace. These are assembled and formatted the same way they would be if passed to the [`console.log()`](log) method.

## Example

    function foo() {
      function bar() {
        console.trace();
      }
      bar();
    }

    foo();

In the console, the following trace will be displayed:

    bar
    foo
    <anonymous>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://console.spec.whatwg.org/#trace">Console API<br />
<span class="small">The definition of 'console.trace()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`trace`

1

12

6

11

11

4

1

18

6

11

3.2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Console/trace" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Console/trace</a>
