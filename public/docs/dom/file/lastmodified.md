# File.lastModified

The `File.lastModified` read-only property provides the last modified date of the file as the number of milliseconds since the Unix epoch (January 1, 1970 at midnight). Files without a known last modified date return the current date.

## Syntax

    const time = instanceOfFile.lastModified;

### Value

A number that represents the number of milliseconds since the Unix epoch.

## Example

### Reading from file input

    <input type="file" multiple id="fileInput">

    const fileInput = document.querySelector('#fileInput');
    fileInput.addEventListener('change', (event) => {
      // files is a FileList object (similar to NodeList)
      const files = event.target.files;

      for (let file of files) {
        const date = new Date(file.lastModified);
        console.log(`${file.name} has a last modified date of ${date}`);
      }
    });

Try the results out below:

### Dynamically created files

If a File is created dynamically, the last modified time can be supplied in the [`new File()`](file) constructor function. If it is missing, `lastModified` inherits the current time from [`Date.now()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/now) at the moment the `File` object gets created.

    const fileWithDate = new File([], 'file.bin', {
      lastModified: new Date(2017, 1, 1),
    });
    console.log(fileWithDate.lastModified); //returns 1485903600000

    const fileWithoutDate = new File([], 'file.bin');
    console.log(fileWithoutDate.lastModified); //returns current time

## Reduced time precision

To offer protection against timing attacks and fingerprinting, the precision of `someFile.lastModified` might get rounded depending on browser settings.  
In Firefox, the `privacy.reduceTimerPrecision` preference is enabled by default and defaults to 20us in Firefox 59; in 60 it will be 2ms.

    // reduced time precision (2ms) in Firefox 60
    someFile.lastModified;
    // 1519211809934
    // 1519211810362
    // 1519211811670
    // ...

    // reduced time precision with `privacy.resistFingerprinting` enabled
    someFile.lastModified;
    // 1519129853500
    // 1519129858900
    // 1519129864400
    // ...

In Firefox, you can also enabled `privacy.resistFingerprinting`, the precision will be 100ms or the value of `privacy.resistFingerprinting.reduceTimerPrecision.microseconds`, whichever is larger.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#file-attrs">File API<br />
<span class="small">The definition of 'lastModified' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`lastModified`

13

18

15

No

16

10

≤37

Yes

No

No

10

Yes

## See also

- [`File`](../file)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/File/lastModified" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/File/lastModified</a>
