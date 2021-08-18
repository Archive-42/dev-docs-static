# Console.groupCollapsed()

Creates a new inline group in the Web Console. Unlike [`console.group()`](group), however, the new group is created collapsed. The user will need to use the disclosure button next to it to expand it, revealing the entries created in the group.

Call [`console.groupEnd()`](groupend) to back out to the parent group.

See [Using groups in the console](../console#using_groups_in_the_console) in the [`console`](../console) documentation for details and examples.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    console.groupCollapsed([label]);

## Parameters

`label`  
Label for the group. Optional.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://console.spec.whatwg.org/#groupcollapsed">Console API<br />
<span class="small">The definition of 'console.groupCollapsed()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Console/groupCollapsed" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Console/groupCollapsed</a>
