# msFirstPaint

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

`msFirstPaint` is a read-only property which gets the time when the document loaded by the window object began to be displayed to the user.

Put another way, `msFirstPaint` utilizes the browser to measure when the first content completes being painted in the window. It is available from javascript and can be reported from the field.

This proprietary property is specific to Internet Explorer and Microsoft Edge.

## Syntax

    p = object.msFirstPaint;

## Value

An Integer value that represents the time when the document began to be displayed or 0 if the document could not be loaded.

The numerical value reported represents the number of milliseconds between the recorded time and midnight January 1, 1970 (UTC).

This property is supported only for documents displayed in IE9 Standards mode.

## Example

The following example shows how to calculate the time that is required to request the document before the document begins to display for the user.

      var oTiming = window.performance.timing;
      var iTimeMS = oTiming.msFirstPaint - oTiming.navigationStart;

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MsFirstPaint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MsFirstPaint</a>
