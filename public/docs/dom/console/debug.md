# console.debug()

The [`console`](../console) method `debug()` outputs a message to the web console at the "debug" log level. The message is only displayed to the user if the console is configured to display debug output. In most cases, the log level is configured within the console UI. This log level might correspond to the \`Debug\` or \`Verbose\` log level

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    console.debug(obj1 [, obj2, ..., objN]);
    console.debug(msg [, subst1, ..., substN]);

### Parameters

`obj1` ... `objN`  
A list of JavaScript objects to output. The string representations of each of these objects are appended together in the order listed and output to the console.

`msg`  
A JavaScript string containing zero or more substitution strings, which are replaced with `subst1` through `substN` in consecutive order.

`subst1` ... `substN`  
JavaScript objects with which to replace substitution strings within `msg`. This gives you additional control over the format of the output. See [Using string substitutions](../console#using_string_substitutions) in [console](../console) for a description of how substitutions work.

See [Outputting text to the console](../console#outputting_text_to_the_console) in the documentation of the [`console`](../console) object for details.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://console.spec.whatwg.org/#debug">Console API<br />
<span class="small">The definition of 'console.debug()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`debug`

1

12

4

10

11

4

1

18

4

11

3.2

1.0

`substitution_strings`

1

In version 28, if a negative value is passed to `%d`, it will be rounded down to the closest negative integer. For example, -0.1 becomes -1.

12

\["Before Edge 79, `%c` is not supported.", "Before Edge 79, `%d` outputs a 0 if the specified value isn't a number."\]

9

10

\["`%c` is not supported.", "`%d` outputs a 0 if the specified value isn't a number."\]

15

4

1

In version 28, if a negative value is passed to `%d`, it will be rounded down to the closest negative integer. For example, -0.1 becomes -1.

18

In version 28, if a negative value is passed to `%d`, it will be rounded down to the closest negative integer. For example, -0.1 becomes -1.

9

14

3.2

1.0

In Samsung Internet 1.5, if a negative value is passed to `%d`, it will be rounded down to the closest negative integer. For example, -0.1 becomes -1.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Console/debug" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Console/debug</a>
