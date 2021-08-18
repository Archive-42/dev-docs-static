# scan

The `scan` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test the scanning process (if any) utilized by the output device. The word _scanning_ used in this context does not refer to an image scanner, such as one used to digitize a photograph. Rather, it means the process by which an image is painted onto a television screen (or other device).

## Syntax

The `scan` feature is specified as a single keyword value chosen from the list below.

`interlace`  
The device draws odd lines and even lines alternately. Some televisions use interlaced scanning.

`progressive`  
The device draws all lines in sequence. All computer screens use progressive scanning.

## Examples

### HTML

    <p>If your screen uses interlaced rendering, this text should
       be in a sans-serif font. If your screen uses progressive
       scanning, you should see a serif font.</p>

### CSS

    p {
      font-family: cursive;
    }

    @media (scan: interlace) {
      p {
        font-family: sans-serif;
      }
    }

    @media (scan: progressive) {
      p {
        font-family: serif;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#scan">Media Queries Level 4<br />
<span class="small">The definition of 'scan' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/mediaqueries-3/#scan">Media Queries<br />
<span class="small">The definition of 'scan' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`scan`

No

No

No

No

No

No

No

No

No

No

No

No

## See also

- [Using Media Queries](../media_queries/using_media_queries)
- [@media](../@media)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/scan" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/scan</a>
