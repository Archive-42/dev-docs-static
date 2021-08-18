# Console.countReset()

The `console.countReset()` method resets counter used with [`console.count()`](count).

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    console.countReset([label]);

### Parameters

`label` <span class="badge inline optional">Optional</span>  
A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String). If supplied, `countReset()` resets the count for that label to 0. If omitted, `countReset()` resets the default counter to 0.

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
    console.countReset();

Console output will look something like this:

    "default: 1"
    "default: 2"
    "default: 3"
    "default: 4"
    "default: 0"

Note that the call to `console.counterReset()` resets the value of the default counter to zero.

If we pass the `user` variable as the `label` argument with the string "bob" to the first invocation of `count()`, and the string "alice" to the second:

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
    console.countReset("bob");
    console.count("alice");

We will see output like this:

    "bob: 1"
    "alice: 1"
    "alice: 2"
    "bob: 0"
    "alice: 3"

Resetting the value of the counter "bob" only changes the value of that counter. The value of "alice" is unchanged.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://console.spec.whatwg.org/#count">Console API<br />
<span class="small">The definition of 'console.countReset()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`countReset`

68

79

62

No

55

13

68

68

62

48

13

10.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Console/countReset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Console/countReset</a>
