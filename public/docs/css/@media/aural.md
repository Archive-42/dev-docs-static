# aural

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `aural` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media type](../@media#media_types) is used for devices that have speech output capabilities.

**Note:** This media type has been deprecated in favor of `speech`.

## Syntax

The `aural` CSS media type—which has been deprecated in favor of the `speech` media type—was used to specify a block of CSS that applied only when the content is being presented using a speech synthesis device.

    @media aural {
      /* speech-specific styles here */
    }

Updating existing CSS to use the `speech` media type should be as simple as replacing `aural` with `speech`.

## Examples

### Basic example

    @media aural {
      body { voice-family: Paul }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/CSS22/">CSS Level 2 (Revision 2)<br />
<span class="small">The definition of 'aural' in that specification.</span></a></td><td>Deprecated</td><td>Initial definition.</td></tr></tbody></table>

## See also

- [Media queries](../media_queries)
- [Using media queries](../media_queries/using_media_queries)
- `@media`
- `speech`

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/aural" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/aural</a>
