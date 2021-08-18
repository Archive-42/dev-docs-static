# Console.group()

Creates a new inline group in the [Web Console](https://developer.mozilla.org/en-US/docs/Tools/Web_Console) log. This indents following console messages by an additional level, until [`console.groupEnd()`](groupend) is called.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    console.group([label]);

## Parameters

`label`  
Label for the group. Optional. (Chrome 59 tested) Does not work with `console.groupEnd()`.

### Using groups in the console

<span class="indicatorInHeadline minVer geckoMinVerMethod">Requires Gecko 9.0(Firefox 9.0 / Thunderbird 9.0 / SeaMonkey 2.6)</span>

You can use nested groups to help organize your output by visually associating related messages. To create a new nested block, call `console.group()`. The `console.groupCollapsed()` method is similar, but the new block is collapsed and requires clicking a disclosure button to read it.

**Note:** From Gecko 9 until Gecko 51, the `groupCollapsed()` method was the same as `group()`. Collapsed groups are fully supported starting in Gecko 52. See [bug 1088360](https://bugzilla.mozilla.org/show_bug.cgi?id=1088360).

To exit the current group, call `console.groupEnd()`. For example, given this code:

    console.log("This is the outer level");
    console.group();
    console.log("Level 2");
    console.group();
    console.log("Level 3");
    console.warn("More of level 3");
    console.groupEnd();
    console.log("Back to level 2");
    console.groupEnd();
    console.log("Back to the outer level");

The output looks like this:

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAARcAAACdCAMAAACpUczsAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAKvUExURf//////8f///Pr/////94CAgPH//8vLy39/fwAAANf2//f/////+fDw8d2ziR+Iz/j8/+fn5rOFfv78+ers7v/32M+SOaza836LuPf4+qurqqvX89/5/+r+//z///jy8bLa9PL08riNfuG7mfL5/r6QfoV/gIm54P/3y/jbr//63//78fDy+IjO8suefe7///f48f/93riDfot/f/bUkPz49X6Bsp9/f/nt2ZAuAPL3+H9/l//+6cHo+36BhX9/kcbz/9SSOXyhy7Xf+ZfF572Ifn5/o+G5jeHa3Lzh+ub7/39/iwAAL6vb+AAAj/TOiUEAQ5N/fvz+/P725QA/nDyPy4Sq1Priu/DeyPHWroOv3Mimj//50AAAafX79r/w///x0qzN55m62KLJ5cLBxVAAAP/xxLyWfvfet/fv7C8AAH2Uvszy/8+WUeDi7+bPrH7E7+3XugAAQgB4wABFjerq6q1jAAAAgoSLpujs8lqi1Pzpz14AALy8uQCFy5ouAIilxPHg1sbk+PT05ufy+ZnU8IWcts+OINfn8c3c7talXfz3919ZT/3ltNft+gArlsvT4wAAUIwAAKHW8rShjf7qxeTCkGoAAM6qgwBZqoFIANr6/65/fgAAXvzcodD7/22y3EIALnqt2unIm51TANbL07nU6e/BdGJWMdmZOPHSo0IAAM/LywBqtQBlquSxaUtPUSGBys/BwdS3l3sAAMd7AH7B3KZ/f7jg8dzu8n2XnMCEI0teYNn59rZzANrU3vDs6kul28CzmqWgoIdiT5eFfylipI63zKxuRoJBRDw8LZpmKABUmNerc5xBAAAsbx6Q0e/v3ePx97WCVTUuAFyGrmCXxVA7AKqMfL/M4kBPXABBUHIuAL+dZuC/f97CqyGFwQAuOHIuLXFAei4AL/yZxyYAAA6dSURBVHja7J35XxNXAsDfTPKJ8wgBUgTlFg/OcChRUEA5FBQRRE4pCCqoRbyQYwui4i4ieIICouJtRalHrbJaXbvudl3WtVat1rpbr3b/kH1vJjMESMyEDLVJ3/uBZN6RZL5513zzeAPAaIUxbAAk/E640OGTxWWcrvEeOHD2dRLJhToXxj3J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" alt="A screenshot of messages nested in the console output." width="279" height="157" />

See [Using groups in the console](../console#using_groups_in_the_console) in the documentation of [`console`](../console) for more details.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://console.spec.whatwg.org/#group">Console API<br />
<span class="small">The definition of 'console.group()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Console/group" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Console/group</a>
