# font-variant-ligatures

The `font-variant-ligatures` CSS property controls which [ligatures](https://developer.mozilla.org/en-US/docs/Glossary/Ligature) and <span class="page-not-created">contextual forms</span> are used in textual content of the elements it applies to. This leads to more harmonized forms in the resulting text.

## Syntax

    /* Keyword values */
    font-variant-ligatures: normal;
    font-variant-ligatures: none;
    font-variant-ligatures: common-ligatures;           /* <common-lig-values> */
    font-variant-ligatures: no-common-ligatures;        /* <common-lig-values> */
    font-variant-ligatures: discretionary-ligatures;    /* <discretionary-lig-values> */
    font-variant-ligatures: no-discretionary-ligatures; /* <discretionary-lig-values> */
    font-variant-ligatures: historical-ligatures;       /* <historical-lig-values> */
    font-variant-ligatures: no-historical-ligatures;    /* <historical-lig-values> */
    font-variant-ligatures: contextual;                 /* <contextual-alt-values> */
    font-variant-ligatures: no-contextual;              /* <contextual-alt-values> */

    /* Global values */
    font-variant-ligatures: inherit;
    font-variant-ligatures: initial;
    font-variant-ligatures: unset;

The `font-variant-ligatures` property is specified as one of the keyword values listed below.

### Values

`normal`  
This keyword leads to the activation of the usual ligatures and contextual forms needed for correct rendering. The ligatures and forms activated depend on the font, language and kind of script. This is the default value.

`none`  
This keyword specifies that all ligatures and contextual forms are disabled, even common ones.

_&lt;common-lig-values&gt;_  
These values control the most common ligatures, like for `fi`, `ffi`, `th` or similar. They correspond to the OpenType values `liga` and `clig`. Two values are possible:

- `common-ligatures` activating these ligatures. Note that the keyword `normal` activates these ligatures.
- `no-common-ligatures` deactivating these ligatures.

_&lt;discretionary-lig-values&gt;_  
These values control specific ligatures, specific to the font and defined by the type designer. They correspond to the OpenType values `dlig`. Two values are possible:

- `discretionary-ligatures` activating these ligatures.
- `no-discretionary-ligatures` deactivating the ligatures. Note that the keyword `normal` usually deactivates these ligatures.

_&lt;historical-lig-values&gt;_  
These values control the ligatures used historically, in old books, like the German tz digraph being displayed as ꜩ. They correspond to the OpenType values `hlig`. Two values are possible:

- `historical-ligatures` activating these ligatures.
- `no-historical-ligatures` deactivating the ligatures. Note that the keyword `normal` usually deactivates these ligatures.

_&lt;contextual-alt-values&gt;_  
These values control whether letters adapt to their context—that is, whether they adapt to the surrounding letters. These values correspond to the OpenType values `calt`. Two values are possible:

- `contextual` specifies that the contextual alternates are to be used. Note that the keyword `normal` usually activates these ligatures too.
- `no-contextual` prevents their use.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | none | [ <common-lig-values> || <discretionary-lig-values> || <historical-lig-values> || <contextual-alt-values> ]where
    <common-lig-values> = [ common-ligatures | no-common-ligatures ]
    <discretionary-lig-values> = [ discretionary-ligatures | no-discretionary-ligatures ]
    <historical-lig-values> = [ historical-ligatures | no-historical-ligatures ]
    <contextual-alt-values> = [ contextual | no-contextual ]

## Examples

### Setting font ligatures and contextual forms

#### HTML

    <link href="//fonts.googleapis.com/css?family=Lora" rel="stylesheet">
    <p class="normal">
      normal<br>
      if fi ff tf ft jf fj
    </p>
    <p class="none">
      none<br>
      if fi ff tf ft jf fj
    </p>
    <p class="common-ligatures">
      common-ligatures<br>
      if fi ff tf ft jf fj
    </p>
    <p class="no-common-ligatures">
      no-common-ligatures<br>
      if fi ff tf ft jf fj
    </p>
    <p class="discretionary-ligatures">
      discretionary-ligatures<br>
      if fi ff tf ft jf fj
    </p>
    <p class="no-discretionary-ligatures">
      no-discretionary-ligatures<br>
      if fi ff tf ft jf fj
    </p>
    <p class="historical-ligatures">
      historical-ligatures<br>
      if fi ff tf ft jf fj
    </p>
    <p class="no-historical-ligatures">
      no-historical-ligatures<br>
      if fi ff tf ft jf fj
    </p>
    <p class="contextual">
      contextual<br>
      if fi ff tf ft jf fj
    </p>
    <p class="no-contextual">
      no-contextual<br>
      if fi ff tf ft jf fj
    </p>
    <p class="contextual">
      contextual<br>
      if fi ff tf ft jf fj
    </p>

#### CSS

    p {
      font-family: Lora, serif;
    }
    .normal {
      font-variant-ligatures: normal;
    }

    .none {
      font-variant-ligatures: none;
    }

    .common-ligatures {
      font-variant-ligatures: common-ligatures;
    }

    .no-common-ligatures {
      font-variant-ligatures: no-common-ligatures;
    }

    .discretionary-ligatures {
      font-variant-ligatures: discretionary-ligatures;
    }

    .no-discretionary-ligatures {
      font-variant-ligatures: no-discretionary-ligatures;
    }

    .historical-ligatures {
      font-variant-ligatures: historical-ligatures;
    }

    .no-historical-ligatures {
      font-variant-ligatures: no-historical-ligatures;
    }

    .contextual {
      font-variant-ligatures: contextual;
    }

    .no-contextual {
      font-variant-ligatures: no-contextual;
    }

    .contextual {
      font-variant-ligatures: contextual;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-3/#propdef-font-variant-ligatures">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'font-variant-ligatures' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`font-variant-ligatures`

34

31

79

79

34

No

21

19

9.1

7

37

4.4

34

34

21

19

9.3

7

2.0

## See Also

- [`font-variant-alternates`](font-variant-alternates)
- [`font-variant-caps`](font-variant-caps)
- [`font-variant-east-asian`](font-variant-east-asian)
- [`font-variant`](font-variant)
- [`font-variant-numeric`](font-variant-numeric)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-ligatures" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-ligatures</a>
