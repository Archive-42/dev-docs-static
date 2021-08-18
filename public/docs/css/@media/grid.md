# grid

The `grid` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) can be used to test whether the output device uses a grid-based screen.

Most modern computers and smartphones have bitmap-based screens. Examples of grid-based devices include text-only terminals and basic phones with only one fixed font.

## Syntax

The `grid` feature is specified as a [`<mq-boolean>`](../media_queries/using_media_queries) value (`0` or `1`) representing whether or not the output device is grid-based.

## Examples

### HTML

    <p class="unknown">I don't know if you're using a grid device. :-(</p>
    <p class="bitmap">You are using a bitmap device.</p>
    <p class="grid">You are using a grid device! Neato!</p>

### CSS

    :not(.unknown) {
      color: lightgray;
    }

    @media (grid: 0) {
      .unknown {
        color: lightgray;
      }

      .bitmap {
        color: red;
        text-transform: uppercase;
      }
    }

    @media (grid: 1) {
      .unknown {
        color: lightgray;
      }

      .grid {
        color: black;
        text-transform: uppercase;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#grid">Media Queries Level 4<br />
<span class="small">The definition of 'grid' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/mediaqueries-3/#grid">Media Queries<br />
<span class="small">The definition of 'grid' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`grid`

1

12

2

10

10

3

≤37

18

4

10.1

1

1.0

## See also

- [Using Media Queries](../media_queries/using_media_queries)
- [@media](../@media)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/grid" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/grid</a>
