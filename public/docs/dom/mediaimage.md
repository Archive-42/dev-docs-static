# MediaImage

The Media Session API's `MediaImage` dictionary describes the images associated with a media resource's [`MediaMetadata`](mediametadata). Its contents can be displayed by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) in appropriate contexts like in a player interface to show the current playing video or audio track.

## Properties

<span class="page-not-created">`src`</span>  
The URL from which the user agent fetches the image's data.

<span class="page-not-created">`sizes`</span>  
Specifies the resource in multiple sizes so the user agent doesn't have to scale a single image.

<span class="page-not-created">`type`</span>  
The [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) hint for the user agent that allows it to ignore images of types that it doesn't support. However, the user agent may still use MIME type sniffing after downloading the image to determine its type.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediasession/#dictdef-mediaimage">Media Session Standard<br />
<span class="small">The definition of 'MediaImage' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.MediaImage`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [`MediaMetadata.artwork`](mediametadata/artwork)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaImage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaImage</a>
