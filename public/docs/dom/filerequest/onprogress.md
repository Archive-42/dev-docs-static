# FileRequest.onprogress

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

## Summary

This property specifies a callback function to be run repeatedly while the operation represented by a [`FileRequest`](../filerequest) object is in progress.

## Syntax

    instanceOfFileRequest.onprogress = function;

Where `instanceOfFileRequest` is a [`FileRequest`](../filerequest) object and `function` is the JavaScript function to execute.

Each time the function callback is called, it gets an object as its first parameter. Those objects contain two properties:

`loaded`  
A number representing the current amount of bytes processed by the operation.

`total`  
A number representing the total amount of bytes that will be processed by the operation.

## Example

    // Assuming 'request' which is a FileRequest object

    request.onprogress = function (status) {
      var progress = document.querySelector('progress');

      progress.value = status.loaded;
      progress.max   = status.total;
    }

## Specifications

Not part of any current specification.

## See also

- <span class="page-not-created">`DOMRequest`</span>
- [`LockedFile`](../lockedfile)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileRequest/onprogress" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileRequest/onprogress</a>
