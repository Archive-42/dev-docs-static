# console.count()

The `console.count()` method logs the number of times that this particular call to `count()` has been called.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    console.count([label]);

### Parameters

`label` <span class="badge inline optional">Optional</span>  
A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String). If supplied, `count()` outputs the number of times it has been called with that label. If omitted, `count()` behaves as though it was called with the "default" label.

## Examples

For example, given code like this:

    let user = "";

    function greet() {
      console.count();
      return "hi " + user;
    }

    user = "bob";
    greet();
    user = "alice";
    greet();
    greet();
    console.count();

Console output will look something like this:

    "default: 1"
    "default: 2"
    "default: 3"
    "default: 4"

The label is displayed as `default` because no explicit label was supplied.

If we pass the `user` variable as the `label` argument to the first invocation of `count()`, and the string "alice" to the second:

    let user = "";

    function greet() {
      console.count(user);
      return "hi " + user;
    }

    user = "bob";
    greet();
    user = "alice";
    greet();
    greet();
    console.count("alice");

We will see output like this:

    "bob: 1"
    "alice: 1"
    "alice: 2"
    "alice: 3"

We're now maintaining separate counts based only on the value of `label`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://console.spec.whatwg.org/#count">Console API<br />
<span class="small">The definition of 'console.count()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`count`

1

12

30

11

11

4

1

18

30

11

3.2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Console/count" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Console/count</a>
