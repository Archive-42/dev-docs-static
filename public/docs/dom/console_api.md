# Console API

The Console API provides functionality to allow developers to perform debugging tasks, such as logging messages or the values of variables at set points in your code, or timing how long an operation takes to complete.

**Note:** This feature is available in [Web Workers](web_workers_api).

## Concepts and usage

The Console API started as a largely proprietary API, with different browsers implementing it, albeit it in inconsistent ways. [The Console API spec](https://console.spec.whatwg.org/) was created to define consistent behavior, and all modern browsers eventually settled on implementing this behavior — although some implementations still have their own additional proprietary functions. Find out about these at:

- [Google Chrome DevTools implementation](https://developers.google.com/chrome-developer-tools/docs/console-api)
- [Safari DevTools implementation](https://developer.apple.com/library/safari/documentation/AppleApplications/Conceptual/Safari_Developer_Guide/Console/Console.html)

Usage is very simple — the [`console`](console) object — available via [`window.console`](window/console), or [`WorkerGlobalScope.console`](workerglobalscope/console) in workers; accessible using just `console` — contains many methods that you can call to perform rudimentary debugging tasks, generally focused around logging various values to the browser's [Web Console](https://developer.mozilla.org/en-US/docs/Tools/Web_Console).

By far the most commonly-used method is [`console.log`](console/log), which is used to log the current value contained inside a specific variable.

## Interfaces

[`console`](console)  
Provides rudimentary debugging functionality, including logging, stack traces, timers, and counters.

## Examples

    let myString = 'Hello world';

    // Output "Hello world" to the console
    console.log(myString)

See the [Console reference page](console#usage) for more examples.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://console.spec.whatwg.org/">Console API</a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Console_API`

1

12

4

8

In Internet Explorer 8 and 9, the `console` object is `undefined` when the developer tools are not open. This behavior was fixed in Internet Explorer 10.

10.5

3

1

18

4

11

1

1.0

`assert`

1

12

28

8

11

4

1

18

28

11

3.2

1.0

`clear`

25

12

39

8

12

6.1

≤37

25

39

12

7

1.5

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

`dir`

1

12

8

9

11

4

1

18

8

11

3.2

1.0

`dirxml`

1

12

39

11

11

4

1

18

39

11

3.2

1.0

`error`

1

12

4

8

10.5

3

1

18

4

11

1

1.0

`exception`

No

13-79

28

No

No

No

No

No

28

?

No

No

`group`

1

12

4

11

11

4

37

18

4

11

3.2

1.0

`groupCollapsed`

6

12

9

11

11

5.1

37

18

9

11

5.1

1.0

`groupEnd`

1

12

9

11

11

4

37

18

9

11

3.2

1.0

`info`

1

12

4

8

10.5

3

1

18

4

11

1

1.0

`log`

1

12

4

8

10.5

3

1

18

4

11

1

1.0

`profile`

4

12

16

9

11

4

≤37

18

16

11

3.2

1.0

`profileEnd`

4

12

16

9

11

4

≤37

18

16

11

3.2

1.0

`table`

27

13

34

No

11

6.1

≤37

27

34

11

7

1.5

`time`

1

12

10

11

11

4

1

18

10

11

3.2

1.0

`timeEnd`

1

12

10

11

11

4

1

18

10

11

3.2

1.0

`timeLog`

71

79

62

No

60

13

71

71

62

50

13

10.0

`timeStamp`

14

12

39

11

15

6

≤37

18

39

14

6

1.0

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

`warn`

1

12

4

8

10.5

3

1

18

4

11

1

1.0

`worker_support`

31

12

29

10

≤12.1

6.1

4.4.3

31

29

≤12.1

7

2.0

## See also

- [Tools](https://developer.mozilla.org/en-US/docs/Tools)
- [Web Console](https://developer.mozilla.org/en-US/docs/Tools/Web_Console) — how the Web Console in Firefox handles console API calls
- [Remote debugging](https://developer.mozilla.org/en-US/docs/Tools/Remote_Debugging) — how to see console output when the debugging target is a mobile device

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Console_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Console_API</a>
