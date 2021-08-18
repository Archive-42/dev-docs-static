# FileReader.readyState

The [`FileReader`](../filereader) `readyState` property provides the current state of the reading operation a `FileReader` is in. A `FileReader` exists in one of the following states:

Value

State

Description

`0`

`EMPTY`

Reader has been created. None of the read methods called yet.

`1`

`LOADING`

A read method has been called.

`2`

`DONE`

The operation is complete.

`EMPTY`  
The `FileReader` has been created, but no readAs method was called yet.

`LOADING`  
A readAs method was invoked. A [`File`](../file) or [`Blob`](../blob) is being read, and no error has occurred yet.

`DONE`  
The read operation is complete. This could mean that: the entire [`File`](../file) or [`Blob`](../blob) has been read into memory, a file read error occurred, or [`abort()`](abort) was called and the read was cancelled.

## Example

    var reader = new FileReader();
    console.log('EMPTY', reader.readyState); // readyState will be 0

    reader.readAsText(blob);
    console.log('LOADING', reader.readyState); // readyState will be 1

    reader.onloadend = function () {
      console.log('DONE', reader.readyState); // readyState will be 2
    };

## Value

A number which is one of the three possible state constants define for the [`FileReader`](../filereader) API.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#dom-filereader-readystate">File API<br />
<span class="small">The definition of 'readyState' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`readyState`

7

12

3.6

10

11

6.1

≤37

Yes

32

11

6.1

Yes

## See also

- [`Blob`](../blob)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readyState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readyState</a>
