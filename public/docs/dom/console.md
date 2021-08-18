# console

The `console` object provides access to the browser's debugging console (e.g. the [Web Console](https://developer.mozilla.org/en-US/docs/Tools/Web_Console) in Firefox). The specifics of how it works varies from browser to browser, but there is a _de facto_ set of features that are typically provided.

The `console` object can be accessed from any global object. [`Window`](window) on browsing scopes and [`WorkerGlobalScope`](workerglobalscope) as specific variants in workers via the property console. It's exposed as [`Window.console`](window/console), and can be referenced as `console`. For example:

    console.log("Failed to open the specified link")

This page documents the [Methods](#methods) available on the `console` object and gives a few [Usage](#usage) examples.

**Note:** This feature is available in [Web Workers](web_workers_api).

**Note**: The actual `console` interface is defined as all lower case (i.e. not `Console`), for historical reasons.

## Methods

[`console.assert()`](console/assert)  
Log a message and stack trace to console if the first argument is `false`.

[`console.clear()`](console/clear)  
Clear the console.

[`console.count()`](console/count)  
Log the number of times this line has been called with the given label.

[`console.countReset()`](console/countreset)  
Resets the value of the counter with the given label.

[`console.debug()`](console/debug)  
Outputs a message to the console with the log level `debug`.

[`console.dir()`](console/dir)  
Displays an interactive listing of the properties of a specified JavaScript object. This listing lets you use disclosure triangles to examine the contents of child objects.

[`console.dirxml()`](console/dirxml)  
Displays an XML/HTML Element representation of the specified object if possible or the JavaScript Object view if it is not possible.

[`console.error()`](console/error)  
Outputs an error message. You may use [string substitution](#using_string_substitutions) and additional arguments with this method.

<span class="page-not-created">`console.exception()`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
An alias for `error()`.

[`console.group()`](console/group)  
Creates a new inline [group](#using_groups_in_the_console), indenting all following output by another level. To move back out a level, call `groupEnd()`.

[`console.groupCollapsed()`](console/groupcollapsed)  
Creates a new inline [group](#using_groups_in_the_console), indenting all following output by another level. However, unlike `group()` this starts with the inline group collapsed requiring the use of a disclosure button to expand it. To move back out a level, call `groupEnd()`.

[`console.groupEnd()`](console/groupend)  
Exits the current inline [group](#using_groups_in_the_console).

[`console.info()`](console/info)  
Informative logging of information. You may use [string substitution](#using_string_substitutions) and additional arguments with this method.

[`console.log()`](console/log)  
For general output of logging information. You may use [string substitution](#using_string_substitutions) and additional arguments with this method.

[`console.profile()`](console/profile) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Starts the browser's built-in profiler (for example, the [Firefox performance tool](https://developer.mozilla.org/en-US/docs/Tools/Performance)). You can specify an optional name for the profile.

[`console.profileEnd()`](console/profileend) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Stops the profiler. You can see the resulting profile in the browser's performance tool (for example, the [Firefox performance tool](https://developer.mozilla.org/en-US/docs/Tools/Performance)).

[`console.table()`](console/table)  
Displays tabular data as a table.

[`console.time()`](console/time)  
Starts a [timer](#timers) with a name specified as an input parameter. Up to 10,000 simultaneous timers can run on a given page.

[`console.timeEnd()`](console/timeend)  
Stops the specified [timer](#timers) and logs the elapsed time in milliseconds since it started.

[`console.timeLog()`](console/timelog)  
Logs the value of the specified [timer](#timers) to the console.

[`console.timeStamp()`](console/timestamp) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Adds a marker to the browser's [Timeline](https://developer.chrome.com/devtools/docs/timeline) or [Waterfall](https://developer.mozilla.org/en-US/docs/Tools/Performance/Waterfall) tool.

[`console.trace()`](console/trace)  
Outputs a [stack trace](#stack_traces).

[`console.warn()`](console/warn)  
Outputs a warning message. You may use [string substitution](#using_string_substitutions) and additional arguments with this method.

## Examples

### Outputting text to the console

The most frequently-used feature of the console is logging of text and other data. There are four categories of output you can generate, using the [`console.log()`](console/log), [`console.info()`](console/info), [`console.warn()`](console/warn), and [`console.error()`](console/error) methods respectively. Each of these results in output styled differently in the log, and you can use the filtering controls provided by your browser to only view the kinds of output that interest you.

There are two ways to use each of the output methods; you can pass in a list of objects whose string representations get concatenated into one string, then output to the console, or you can pass in a string containing zero or more substitution strings followed by a list of objects to replace them.

#### Outputting a single object

The simplest way to use the logging methods is to output a single object:

    var someObject = { str: "Some text", id: 5 };
    console.log(someObject);

The output looks something like this:

    [09:27:13.475] ({str:"Some text", id:5})

#### Outputting multiple objects

You can also output multiple objects by listing them when calling the logging method, like this:

    var car = "Dodge Charger";
    var someObject = { str: "Some text", id: 5 };
    console.info("My first car was a", car, ". The object is:", someObject);

This output will look like this:

    [09:28:22.711] My first car was a Dodge Charger . The object is: ({str:"Some text", id:5})

#### Using string substitutions

When passing a string to one of the `console` object's methods that accepts a string (such as `log()`), you may use these substitution strings:

`%o` or `%O`  
Outputs a JavaScript object. Clicking the object name opens more information about it in the inspector.

`%d` or `%i`  
Outputs an integer. Number formatting is supported, for example `console.log("Foo %.2d", 1.1)` will output the number as two significant figures with a leading 0: `Foo 01`

`%s`  
Outputs a string.

`%f`  
Outputs a floating-point value. Formatting is supported, for example `console.log("Foo %.2f", 1.1)` will output the number to 2 decimal places: `Foo 1.10`

**Note**: Precision formatting doesn't work in Chrome

Each of these pulls the next argument after the format string off the parameter list. For example:

    for (var i=0; i<5; i++) {
      console.log("Hello, %s. You've called me %d times.", "Bob", i+1);
    }

The output looks like this:

    [13:14:13.481] Hello, Bob. You've called me 1 times.
    [13:14:13.483] Hello, Bob. You've called me 2 times.
    [13:14:13.485] Hello, Bob. You've called me 3 times.
    [13:14:13.487] Hello, Bob. You've called me 4 times.
    [13:14:13.488] Hello, Bob. You've called me 5 times.

#### Styling console output

You can use the `%c` directive to apply a CSS style to console output:

    console.log("This is %cMy stylish message", "color: yellow; font-style: italic; background-color: blue;padding: 2px");

The text before the directive will not be affected, but the text after the directive will be styled using the CSS declarations in the parameter.

<img src="data:image/png;base64,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" width="198" height="29" />

You may use `%c` multiple times:

    console.log("Multiple styles: %cred %corange", "color: red", "color: orange", "Additional unformatted message");

The properties usable along with the `%c` syntax are as follows (at least, in Firefox — they may differ in other browsers):

- [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) and its longhand equivalents.
- [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) and its longhand equivalents
- [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius)
- [`box-decoration-break`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-decoration-break)
- [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow)
- [`clear`](https://developer.mozilla.org/en-US/docs/Web/CSS/clear) and [`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float)
- [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color)
- [`cursor`](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor)
- [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
- [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) and its longhand equivalents
- [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height)
- [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin)
- [`outline`](https://developer.mozilla.org/en-US/docs/Web/CSS/outline) and its longhand equivalents
- [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding)
- `text-*` properties such as [`text-transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform)
- [`white-space`](https://developer.mozilla.org/en-US/docs/Web/CSS/white-space)
- [`word-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/word-spacing) and [`word-break`](https://developer.mozilla.org/en-US/docs/Web/CSS/word-break)
- [`writing-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode)

**Note**: The console message behaves like an inline element by default. To see the effects of `padding`, `margin`, etc. you should set it to for example `display: inline-block`.

### Using groups in the console

You can use nested groups to help organize your output by visually combining related material. To create a new nested block, call `console.group()`. The `console.groupCollapsed()` method is similar but creates the new block collapsed, requiring the use of a disclosure button to open it for reading.

To exit the current group, call `console.groupEnd()`. For example, given this code:

    console.log("This is the outer level");
    console.group("First group");
    console.log("In the first group");
    console.group("Second group");
    console.log("In the second group");
    console.warn("Still in the second group");
    console.groupEnd();
    console.log("Back to the first group");
    console.groupEnd();
    console.debug("Back to the outer level");

The output looks like this:

<img src="data:image/png;base64,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" alt="Demo of nested groups in Firefox console" width="236" height="169" />

### Timers

You can start a timer to calculate the duration of a specific operation. To start one, call the ` console.time``() ` method, giving it a name as the only parameter. To stop the timer, and to get the elapsed time in milliseconds, just call the `console.timeEnd()` method, again passing the timer's name as the parameter. Up to 10,000 timers can run simultaneously on a given page.

For example, given this code:

    console.time("answer time");
    alert("Click to continue");
    console.timeLog("answer time");
    alert("Do a bunch of other stuff...");
    console.timeEnd("answer time");

Will log the time needed by the user to dismiss the alert box, log the time to the console, wait for the user to dismiss the second alert, and then log the ending time to the console:

<img src="data:image/png;base64,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" class="default internal" width="318" height="102" />

Notice that the timer's name is displayed both when the timer is started and when it's stopped.

**Note:** It's important to note that if you're using this to log the timing for network traffic, the timer will report the total time for the transaction, while the time listed in the network panel is just the amount of time required for the header. If you have response body logging enabled, the time listed for the response header and body combined should match what you see in the console output.

### Stack traces

The console object also supports outputting a stack trace; this will show you the call path taken to reach the point at which you call [`console.trace()`](console/trace). Given code like this:

    function foo() {
      function bar() {
        console.trace();
      }
      bar();
    }

    foo();

The output in the console looks something like this:

<img src="data:image/png;base64,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" width="499" height="123" />

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

`Console`

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

## Notes

- At least in Firefox, if a page defines a `console` object, that object overrides the one built into Firefox.

## See also

- [Firefox Developer Tools](https://developer.mozilla.org/en-US/docs/Tools)
- [Web Console](https://developer.mozilla.org/en-US/docs/Tools/Web_Console) — how the Web Console in Firefox handles console API calls
- [Remote Debugging](https://developer.mozilla.org/en-US/docs/Tools/Remote_Debugging) — how to see console output when the debugging target is a mobile device

### Other implementations

- [Google Chrome DevTools](https://developers.google.com/chrome-developer-tools/docs/console-api)
- [Microsoft Edge DevTools](https://docs.microsoft.com/en-us/microsoft-edge/devtools-guide/console/console-api)
- [Safari Web Inspector](https://developer.apple.com/library/safari/documentation/AppleApplications/Conceptual/Safari_Developer_Guide/Console/Console.html)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Console" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Console</a>
