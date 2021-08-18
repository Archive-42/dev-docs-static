# CSS reference

Use this **CSS reference** to browse an [alphabetical index](#index) of all of the standard [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) properties, [pseudo-classes](pseudo-classes), [pseudo-elements](pseudo-elements), [data types](css_types), [functional notations](css_functions) and [at-rules](at-rule). You can also browse [key CSS concepts](#concepts) and a list of [selectors organized by type](#selectors). Also included is a brief [DOM-CSS / CSSOM reference](#dom-css_cssom).

## Basic rule syntax

### Style rule syntax

    style-rule ::=
        selectors-list {
          properties-list
        }

... where :

    selectors-list ::=
        selector[:pseudo-class] [::pseudo-element]
        [, selectors-list]

    properties-list ::=
        [property : value] [; properties-list]

See the index of [_selectors_](#selectors), [_pseudo-classes_](#pseudo), and _[pseudo-elements](#pseudo)_ below. The syntax for each specified _value_ depends on the data type defined for each specified _property_.

#### Style rule examples

    strong {
      color: red;
    }

    div.menu-bar li:hover > ul {
      display: block;
    }

For a beginner-level introduction to the syntax of selectors, see our [guide on CSS Selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors). Be aware that any [syntax](syntax) error in a rule definition invalidates the entire rule. Invalid rules are ignored by the browser. Note that CSS rule definitions are entirely (ASCII) [text-based](https://www.w3.org/TR/css-syntax-3/#intro), whereas DOM-CSS / CSSOM (the rule management system) is [object-based](https://www.w3.org/TR/cssom/#introduction).

### At-rule syntax

As the structure of at-rules varies widely, please see [At-rule](at-rule) to find the syntax of the specific one you want.

## Index

**Note:** The property names in this index do **not** include the [JavaScript names](css_properties_reference) where they differ from the CSS standard names.

\-

- [`--*`](--*)
- [`-webkit-line-clamp`](-webkit-line-clamp)

A

- [`:active`](:active)
- [`additive-symbols (@counter-style)`](@counter-style/additive-symbols)
- [`::after (:after)`](::after)
- [`align-content`](align-content)
- [`align-items`](align-items)
- [`align-self`](align-self)
- [`align-tracks`](align-tracks)
- [`all`](all)
- <span class="page-not-created">`<an-plus-b>`</span>
- [`<angle>`](angle)
- [`<angle-percentage>`](angle-percentage)
- [`animation`](animation)
- [`animation-delay`](animation-delay)
- [`animation-direction`](animation-direction)
- [`animation-duration`](animation-duration)
- [`animation-fill-mode`](animation-fill-mode)
- [`animation-iteration-count`](animation-iteration-count)
- [`animation-name`](animation-name)
- [`animation-play-state`](animation-play-state)
- [`animation-timing-function`](animation-timing-function)
- [`@annotation`](@font-feature-values#@annotation)
- [`annotation()`](<font-variant-alternates#annotation()>)
- [`:any-link`](:any-link)
- [`appearance`](appearance)
- [`aspect-ratio`](aspect-ratio)
- [`attr()`](<attr()>)

B

- [`::backdrop`](::backdrop)
- [`backdrop-filter`](backdrop-filter)
- [`backface-visibility`](backface-visibility)
- [`background`](background)
- [`background-attachment`](background-attachment)
- [`background-blend-mode`](background-blend-mode)
- [`background-clip`](background-clip)
- [`background-color`](background-color)
- [`background-image`](background-image)
- [`background-origin`](background-origin)
- [`background-position`](background-position)
- [`background-position-x`](background-position-x)
- [`background-position-y`](background-position-y)
- [`background-repeat`](background-repeat)
- [`background-size`](background-size)
- [`<basic-shape>`](basic-shape)
- [`::before (:before)`](::before)
- [`:blank`](:blank)
- [`bleed (@page)`](@page/bleed)
- [`<blend-mode>`](blend-mode)
- <span class="page-not-created">`block-overflow`</span>
- [`block-size`](block-size)
- [`blur()`](<filter-function/blur()>)
- [`border`](border)
- [`border-block`](border-block)
- [`border-block-color`](border-block-color)
- [`border-block-end`](border-block-end)
- [`border-block-end-color`](border-block-end-color)
- [`border-block-end-style`](border-block-end-style)
- [`border-block-end-width`](border-block-end-width)
- [`border-block-start`](border-block-start)
- [`border-block-start-color`](border-block-start-color)
- [`border-block-start-style`](border-block-start-style)
- [`border-block-start-width`](border-block-start-width)
- [`border-block-style`](border-block-style)
- [`border-block-width`](border-block-width)
- [`border-bottom`](border-bottom)
- [`border-bottom-color`](border-bottom-color)
- [`border-bottom-left-radius`](border-bottom-left-radius)
- [`border-bottom-right-radius`](border-bottom-right-radius)
- [`border-bottom-style`](border-bottom-style)
- [`border-bottom-width`](border-bottom-width)
- [`border-collapse`](border-collapse)
- [`border-color`](border-color)
- [`border-end-end-radius`](border-end-end-radius)
- [`border-end-start-radius`](border-end-start-radius)
- [`border-image`](border-image)
- [`border-image-outset`](border-image-outset)
- [`border-image-repeat`](border-image-repeat)
- [`border-image-slice`](border-image-slice)
- [`border-image-source`](border-image-source)
- [`border-image-width`](border-image-width)
- [`border-inline`](border-inline)
- [`border-inline-color`](border-inline-color)
- [`border-inline-end`](border-inline-end)
- [`border-inline-end-color`](border-inline-end-color)
- [`border-inline-end-style`](border-inline-end-style)
- [`border-inline-end-width`](border-inline-end-width)
- [`border-inline-start`](border-inline-start)
- [`border-inline-start-color`](border-inline-start-color)
- [`border-inline-start-style`](border-inline-start-style)
- [`border-inline-start-width`](border-inline-start-width)
- [`border-inline-style`](border-inline-style)
- [`border-inline-width`](border-inline-width)
- [`border-left`](border-left)
- [`border-left-color`](border-left-color)
- [`border-left-style`](border-left-style)
- [`border-left-width`](border-left-width)
- [`border-radius`](border-radius)
- [`border-right`](border-right)
- [`border-right-color`](border-right-color)
- [`border-right-style`](border-right-style)
- [`border-right-width`](border-right-width)
- [`border-spacing`](border-spacing)
- [`border-start-end-radius`](border-start-end-radius)
- [`border-start-start-radius`](border-start-start-radius)
- [`border-style`](border-style)
- [`border-top`](border-top)
- [`border-top-color`](border-top-color)
- [`border-top-left-radius`](border-top-left-radius)
- [`border-top-right-radius`](border-top-right-radius)
- [`border-top-style`](border-top-style)
- [`border-top-width`](border-top-width)
- [`border-width`](border-width)
- [`bottom`](bottom)
- [`@bottom-center`](@page#page-margin-box-type)
- [`box-decoration-break`](box-decoration-break)
- [`box-shadow`](box-shadow)
- [`box-sizing`](box-sizing)
- [`break-after`](break-after)
- [`break-before`](break-before)
- [`break-inside`](break-inside)
- [`brightness()`](<filter-function/brightness()>)

C

- [`calc()`](<calc()>)
- [`caption-side`](caption-side)
- [`caret-color`](caret-color)
- [`@character-variant`](@font-feature-values#@character-variant)
- [`character-variant()`](<font-variant-alternates#character-variant()>)
- [`@charset`](@charset)
- [`:checked`](:checked)
- [`circle()`](<basic-shape#circle()>)
- [`clamp()`](<clamp()>)
- [`clear`](clear)
- [`clip`](clip)
- [`clip-path`](clip-path)
- [`<color>`](color_value)
- [`color`](color)
- [`color-adjust`](color-adjust)
- [`color-scheme`](color-scheme)
- [`column-count`](column-count)
- [`column-fill`](column-fill)
- [`column-gap`](column-gap)
- [`column-rule`](column-rule)
- [`column-rule-color`](column-rule-color)
- [`column-rule-style`](column-rule-style)
- [`column-rule-width`](column-rule-width)
- [`column-span`](column-span)
- [`column-width`](column-width)
- [`columns`](columns)
- [`conic-gradient()`](<conic-gradient()>)
- [`contain`](contain)
- [`content`](content)
- [`content-visibility`](content-visibility)
- [`contrast()`](<filter-function/contrast()>)
- [`<counter>`](<counter()>)
- [`counter-increment`](counter-increment)
- [`counter-reset`](counter-reset)
- [`counter-set`](counter-set)
- [`@counter-style`](@counter-style)
- [`counters()`](<counters()>)
- [`cross-fade()`](<cross-fade()>)
- [`cubic-bezier()`](<easing-function#cubic-bezier()>)
- [`::cue`](::cue)
- [`::cue-region`](::cue-region)
- [`:current`](:current)
- [`cursor`](cursor)
- [`<custom-ident>`](custom-ident)
- [`length#ch`](length#ch)
- [`length#cm`](length#cm)

D

- [`angle#deg`](angle#deg)
- [`:default`](:default)
- [`:defined`](:defined)
- [`<dimension>`](dimension)
- [`:dir`](:dir)
- [`direction`](direction)
- [`:disabled`](:disabled)
- [`display`](display)
- [`<display-box>`](display-box)
- [`<display-inside>`](display-inside)
- [`<display-internal>`](display-internal)
- [`<display-legacy>`](display-legacy)
- [`<display-listitem>`](display-listitem)
- [`<display-outside>`](display-outside)
- [`drop-shadow()`](<filter-function/drop-shadow()>)
- [`resolution#dpcm`](resolution#dpcm)
- [`resolution#dpi`](resolution#dpi)
- [`resolution#dppx`](resolution#dppx)

E

- [`element()`](<element()>)
- [`ellipse()`](<basic-shape#ellipse()>)
- [`:empty`](:empty)
- [`empty-cells`](empty-cells)
- [`:enabled`](:enabled)
- [`env()`](<env()>)
- [`length#em`](length#em)
- [`length#ex`](length#ex)

F

- [`fallback (@counter-style)`](@counter-style/fallback)
- [`filter`](filter)
- [`<filter-function>`](filter-function)
- [`:first`](:first)
- [`:first-child`](:first-child)
- [`::first-letter (:first-letter)`](::first-letter)
- [`::first-line (:first-line)`](::first-line)
- [`:first-of-type`](:first-of-type)
- [`fit-content()`](fit-content)
- [`<flex>`](flex_value)
- [`flex`](flex)
- [`flex-basis`](flex-basis)
- [`flex-direction`](flex-direction)
- [`flex-flow`](flex-flow)
- [`flex-grow`](flex-grow)
- [`flex-shrink`](flex-shrink)
- [`flex-wrap`](flex-wrap)
- [`flex_value#fr`](flex_value#fr)
- [`float`](float)
- [`:focus`](:focus)
- [`:focus-visible`](:focus-visible)
- [`:focus-within`](:focus-within)
- [`font`](font)
- [`font-display (@font-face)`](@font-face/font-display)
- [`@font-face`](@font-face)
- [`font-family`](font-family)
- [`font-family (@font-face)`](@font-face/font-family)
- [`font-feature-settings`](font-feature-settings)
- <span class="page-not-created">`font-feature-settings (@font-face)`</span>
- [`@font-feature-values`](@font-feature-values)
- [`font-kerning`](font-kerning)
- [`font-language-override`](font-language-override)
- [`font-optical-sizing`](font-optical-sizing)
- [`font-size`](font-size)
- [`font-size-adjust`](font-size-adjust)
- [`font-stretch`](font-stretch)
- [`font-stretch (@font-face)`](@font-face/font-stretch)
- [`font-style`](font-style)
- [`font-style (@font-face)`](@font-face/font-style)
- [`font-synthesis`](font-synthesis)
- [`font-variant`](font-variant)
- [`font-variant (@font-face)`](@font-face/font-variant)
- [`font-variant-alternates`](font-variant-alternates)
- [`font-variant-caps`](font-variant-caps)
- [`font-variant-east-asian`](font-variant-east-asian)
- [`font-variant-ligatures`](font-variant-ligatures)
- [`font-variant-numeric`](font-variant-numeric)
- [`font-variant-position`](font-variant-position)
- [`font-variation-settings`](font-variation-settings)
- [`font-variation-settings (@font-face)`](@font-face/font-variation-settings)
- [`font-weight`](font-weight)
- [`font-weight (@font-face)`](@font-face/font-weight)
- [`forced-color-adjust`](forced-color-adjust)
- [`format()`](<@font-face/src#format()>)
- [`<frequency>`](frequency)
- [`<frequency-percentage>`](frequency-percentage)
- [`:fullscreen`](:fullscreen)
- [`:future`](:future)

G

- [`angle#grad`](angle#grad)
- [`gap`](gap)
- [`<gradient>`](gradient)
- [`::grammar-error`](::grammar-error)
- [`grayscale()`](<filter-function/grayscale()>)
- [`grid`](grid)
- [`grid-area`](grid-area)
- [`grid-auto-columns`](grid-auto-columns)
- [`grid-auto-flow`](grid-auto-flow)
- [`grid-auto-rows`](grid-auto-rows)
- [`grid-column`](grid-column)
- [`grid-column-end`](grid-column-end)
- [`grid-column-start`](grid-column-start)
- [`grid-row`](grid-row)
- [`grid-row-end`](grid-row-end)
- [`grid-row-start`](grid-row-start)
- [`grid-template`](grid-template)
- [`grid-template-areas`](grid-template-areas)
- [`grid-template-columns`](grid-template-columns)
- [`grid-template-rows`](grid-template-rows)

H

- [`frequency#Hz`](frequency#hz)
- [`hanging-punctuation`](hanging-punctuation)
- [`:has`](:has)
- [`height`](height)
- [`height (@viewport)`](@viewport)
- <span class="page-not-created">`@historical-forms`</span>
- [`:host()`](<:host()>)
- [`:host-context()`](<:host-context()>)
- [`:hover`](:hover)
- [`hsl()`](<color_value#hsl()>)
- [`hsla()`](<color_value#hsla()>)
- [`hue-rotate()`](<filter-function/hue-rotate()>)
- [`hyphens`](hyphens)

I

- [`<ident>`](ident)
- [`<image>`](image)
- [`image()`](<image#the_image()_functional_notation>)
- [`image-orientation`](image-orientation)
- [`image-rendering`](image-rendering)
- [`image-resolution`](image-resolution)
- [`image-set()`](<image-set()>)
- [`@import`](@import)
- [`:in-range`](:in-range)
- [`:indeterminate`](:indeterminate)
- [`inherit`](inherit)
- [`inherits (@property)`](@property/inherits)
- [`initial`](initial)
- [`initial-letter`](initial-letter)
- [`initial-letter-align`](initial-letter-align)
- [`initial-value (@property)`](@property/initial-value)
- [`inline-size`](inline-size)
- [`inset`](inset)
- [`inset()`](<basic-shape#inset()>)
- [`inset-block`](inset-block)
- [`inset-block-end`](inset-block-end)
- [`inset-block-start`](inset-block-start)
- [`inset-inline`](inset-inline)
- [`inset-inline-end`](inset-inline-end)
- [`inset-inline-start`](inset-inline-start)
- [`<integer>`](integer)
- [`:invalid`](:invalid)
- [`invert()`](<filter-function/invert()>)
- [`:is`](:is)
- [`isolation`](isolation)
- [`length#in`](length#in)

J

- [`justify-content`](justify-content)
- [`justify-items`](justify-items)
- [`justify-self`](justify-self)
- [`justify-tracks`](justify-tracks)

K

- [`frequency#kHz`](frequency#khz)
- [`@keyframes`](@keyframes)

L

- [`:lang`](:lang)
- [`:last-child`](:last-child)
- [`:last-of-type`](:last-of-type)
- <span class="page-not-created">`leader()`</span>
- [`:left`](:left)
- [`left`](left)
- [`@left-bottom`](@page#page-margin-box-type)
- [`<length>`](length)
- [`<length-percentage>`](length-percentage)
- [`letter-spacing`](letter-spacing)
- [`line-break`](line-break)
- <span class="page-not-created">`line-clamp`</span>
- [`line-height`](line-height)
- [`line-height-step`](line-height-step)
- [`linear-gradient()`](<linear-gradient()>)
- [`:link`](:link)
- [`list-style`](list-style)
- [`list-style-image`](list-style-image)
- [`list-style-position`](list-style-position)
- [`list-style-type`](list-style-type)
- [`local()`](<@font-face/src#local()>)
- [`:local-link`](:local-link)

M

- [`length#mm`](length#mm)
- [`margin`](margin)
- [`margin-block`](margin-block)
- [`margin-block-end`](margin-block-end)
- [`margin-block-start`](margin-block-start)
- [`margin-bottom`](margin-bottom)
- [`margin-inline`](margin-inline)
- [`margin-inline-end`](margin-inline-end)
- [`margin-inline-start`](margin-inline-start)
- [`margin-left`](margin-left)
- [`margin-right`](margin-right)
- [`margin-top`](margin-top)
- [`margin-trim`](margin-trim)
- [`::marker`](::marker)
- [`marks (@page)`](@page/marks)
- [`mask`](mask)
- [`mask-border`](mask-border)
- [`mask-border-mode`](mask-border-mode)
- [`mask-border-outset`](mask-border-outset)
- [`mask-border-repeat`](mask-border-repeat)
- [`mask-border-slice`](mask-border-slice)
- [`mask-border-source`](mask-border-source)
- [`mask-border-width`](mask-border-width)
- [`mask-clip`](mask-clip)
- [`mask-composite`](mask-composite)
- [`mask-image`](mask-image)
- [`mask-mode`](mask-mode)
- [`mask-origin`](mask-origin)
- [`mask-position`](mask-position)
- [`mask-repeat`](mask-repeat)
- [`mask-size`](mask-size)
- [`mask-type`](mask-type)
- [`masonry-auto-flow`](masonry-auto-flow)
- [`math-style`](math-style)
- [`matrix()`](<transform-function/matrix()>)
- [`matrix3d()`](<transform-function/matrix3d()>)
- [`max()`](<max()>)
- [`max-block-size`](max-block-size)
- [`max-height`](max-height)
- [`max-height (@viewport)`](@viewport)
- [`max-inline-size`](max-inline-size)
- <span class="page-not-created">`max-lines`</span>
- [`max-width`](max-width)
- [`max-width (@viewport)`](@viewport)
- [`max-zoom (@viewport)`](@viewport)
- [`@media`](@media)
- [`min()`](<min()>)
- [`min-block-size`](min-block-size)
- [`min-height`](min-height)
- [`min-height (@viewport)`](@viewport)
- [`min-inline-size`](min-inline-size)
- [`min-width`](min-width)
- [`min-width (@viewport)`](@viewport)
- [`min-zoom (@viewport)`](@viewport)
- [`minmax()`](<minmax()>)
- [`mix-blend-mode`](mix-blend-mode)
- [`time#ms`](time#ms)

N

- [`@namespace`](@namespace)
- [`negative (@counter-style)`](@counter-style/negative)
- [`:not`](:not)
- [`:nth-child`](:nth-child)
- [`:nth-col`](:nth-col)
- [`:nth-last-child`](:nth-last-child)
- [`:nth-last-col`](:nth-last-col)
- [`:nth-last-of-type`](:nth-last-of-type)
- [`:nth-of-type`](:nth-of-type)
- [`<number>`](number)

O

- [`object-fit`](object-fit)
- [`object-position`](object-position)
- [`offset`](offset)
- [`offset-anchor`](offset-anchor)
- [`offset-distance`](offset-distance)
- [`offset-path`](offset-path)
- [`offset-position`](offset-position)
- [`offset-rotate`](offset-rotate)
- [`:only-child`](:only-child)
- [`:only-of-type`](:only-of-type)
- [`opacity`](opacity)
- [`opacity()`](<filter-function/opacity()>)
- [`:optional`](:optional)
- [`order`](order)
- [`orientation (@viewport)`](@viewport)
- [`@ornaments`](@font-feature-values#@ornaments)
- [`ornaments()`](<font-variant-alternates#ornaments()>)
- [`orphans`](orphans)
- [`:out-of-range`](:out-of-range)
- [`outline`](outline)
- [`outline-color`](outline-color)
- [`outline-offset`](outline-offset)
- [`outline-style`](outline-style)
- [`outline-width`](outline-width)
- [`overflow`](overflow)
- [`overflow-anchor`](overflow-anchor)
- [`overflow-block`](overflow-block)
- [`overflow-clip-margin`](overflow-clip-margin)
- [`overflow-inline`](overflow-inline)
- [`overflow-wrap`](overflow-wrap)
- [`overflow-x`](overflow-x)
- [`overflow-y`](overflow-y)
- [`overscroll-behavior`](overscroll-behavior)
- [`overscroll-behavior-block`](overscroll-behavior-block)
- [`overscroll-behavior-inline`](overscroll-behavior-inline)
- [`overscroll-behavior-x`](overscroll-behavior-x)
- [`overscroll-behavior-y`](overscroll-behavior-y)

P

- [`Pseudo-classes`](pseudo-classes)
- [`Pseudo-elements`](pseudo-elements)
- [`length#pc`](length#pc)
- [`length#pt`](length#pt)
- [`length#px`](length#px)
- [`pad (@counter-style)`](@counter-style/pad)
- [`padding`](padding)
- [`padding-block`](padding-block)
- [`padding-block-end`](padding-block-end)
- [`padding-block-start`](padding-block-start)
- [`padding-bottom`](padding-bottom)
- [`padding-inline`](padding-inline)
- [`padding-inline-end`](padding-inline-end)
- [`padding-inline-start`](padding-inline-start)
- [`padding-left`](padding-left)
- [`padding-right`](padding-right)
- [`padding-top`](padding-top)
- [`@page`](@page)
- [`page-break-after`](page-break-after)
- [`page-break-before`](page-break-before)
- [`page-break-inside`](page-break-inside)
- [`paint()`](<paint()>)
- [`paint-order`](paint-order)
- [`::part`](::part)
- [`:past`](:past)
- [`path()`](<path()>)
- [`:paused`](:paused)
- [`<percentage>`](percentage)
- [`perspective`](perspective)
- [`perspective()`](<transform-function/perspective()>)
- [`perspective-origin`](perspective-origin)
- [`:picture-in-picture`](:picture-in-picture)
- [`place-content`](place-content)
- [`place-items`](place-items)
- [`place-self`](place-self)
- [`::placeholder`](::placeholder)
- [`:placeholder-shown`](:placeholder-shown)
- [`:playing`](:playing)
- [`pointer-events`](pointer-events)
- [`polygon()`](<basic-shape#polygon()>)
- [`<position>`](position_value)
- [`position`](position)
- [`prefix (@counter-style)`](@counter-style/prefix)
- [`@property`](@property)

Q

- [`length#Q`](length#q)
- [`quotes`](quotes)

R

- [`angle#rad`](angle#rad)
- [`length#rem`](length#rem)
- [`radial-gradient()`](<radial-gradient()>)
- [`range (@counter-style)`](@counter-style/range)
- [`<ratio>`](ratio)
- [`:read-only`](:read-only)
- [`:read-write`](:read-write)
- [`rect()`](<shape#rect()>)
- [`repeat()`](<repeat()>)
- [`repeating-linear-gradient()`](<repeating-linear-gradient()>)
- [`repeating-radial-gradient()`](<repeating-radial-gradient()>)
- [`:required`](:required)
- [`resize`](resize)
- [`<resolution>`](resolution)
- [`revert`](revert)
- [`rgb()`](<color_value#rgb()>)
- [`rgba()`](<color_value#rgba()>)
- [`:right`](:right)
- [`right`](right)
- [`@right-bottom`](@page#page-margin-box-type)
- [`:root`](:root)
- [`rotate`](rotate)
- [`rotate()`](<transform-function/rotate()>)
- [`rotate3d()`](<transform-function/rotate3d()>)
- [`rotateX()`](<transform-function/rotatex()>)
- [`rotateY()`](<transform-function/rotatey()>)
- [`rotateZ()`](<transform-function/rotatez()>)
- [`row-gap`](row-gap)
- [`ruby-align`](ruby-align)
- <span class="page-not-created">`ruby-merge`</span>
- [`ruby-position`](ruby-position)

S

- [`saturate()`](<filter-function/saturate()>)
- [`scale`](scale)
- [`scale()`](<transform-function/scale()>)
- [`scale3d()`](<transform-function/scale3d()>)
- [`scaleX()`](<transform-function/scalex()>)
- [`scaleY()`](<transform-function/scaley()>)
- [`scaleZ()`](<transform-function/scalez()>)
- [`:scope`](:scope)
- [`scroll-behavior`](scroll-behavior)
- [`scroll-margin`](scroll-margin)
- [`scroll-margin-block`](scroll-margin-block)
- [`scroll-margin-block-end`](scroll-margin-block-end)
- [`scroll-margin-block-start`](scroll-margin-block-start)
- [`scroll-margin-bottom`](scroll-margin-bottom)
- [`scroll-margin-inline`](scroll-margin-inline)
- [`scroll-margin-inline-end`](scroll-margin-inline-end)
- [`scroll-margin-inline-start`](scroll-margin-inline-start)
- [`scroll-margin-left`](scroll-margin-left)
- [`scroll-margin-right`](scroll-margin-right)
- [`scroll-margin-top`](scroll-margin-top)
- [`scroll-padding`](scroll-padding)
- [`scroll-padding-block`](scroll-padding-block)
- [`scroll-padding-block-end`](scroll-padding-block-end)
- [`scroll-padding-block-start`](scroll-padding-block-start)
- [`scroll-padding-bottom`](scroll-padding-bottom)
- [`scroll-padding-inline`](scroll-padding-inline)
- [`scroll-padding-inline-end`](scroll-padding-inline-end)
- [`scroll-padding-inline-start`](scroll-padding-inline-start)
- [`scroll-padding-left`](scroll-padding-left)
- [`scroll-padding-right`](scroll-padding-right)
- [`scroll-padding-top`](scroll-padding-top)
- [`scroll-snap-align`](scroll-snap-align)
- [`scroll-snap-stop`](scroll-snap-stop)
- [`scroll-snap-type`](scroll-snap-type)
- [`scrollbar-color`](scrollbar-color)
- [`scrollbar-gutter`](scrollbar-gutter)
- [`scrollbar-width`](scrollbar-width)
- [`::selection`](::selection)
- <span class="page-not-created">`selector()`</span>
- [`sepia()`](<filter-function/sepia()>)
- [`<shape>`](shape)
- [`shape-image-threshold`](shape-image-threshold)
- [`shape-margin`](shape-margin)
- [`shape-outside`](shape-outside)
- [`size (@page)`](@page/size)
- [`skew()`](<transform-function/skew()>)
- [`skewX()`](<transform-function/skewx()>)
- [`skewY()`](<transform-function/skewy()>)
- [`::slotted`](::slotted)
- [`speak-as (@counter-style)`](@counter-style/speak-as)
- [`::spelling-error`](::spelling-error)
- [`src (@font-face)`](@font-face/src)
- [`steps()`](<easing-function#steps()>)
- [`<string>`](string)
- [`@styleset`](@font-feature-values#@styleset)
- [`styleset()`](<font-variant-alternates#styleset()>)
- [`@stylistic`](@font-feature-values#@stylistic)
- [`stylistic()`](<font-variant-alternates#stylistic()>)
- [`suffix (@counter-style)`](@counter-style/suffix)
- [`@supports`](@supports)
- [`@swash`](@font-feature-values#@swash)
- [`swash()`](<font-variant-alternates#swash()>)
- [`symbols (@counter-style)`](@counter-style/symbols)
- [`symbols()`](<symbols()>)
- [`syntax (@property)`](@property/syntax)
- [`system (@counter-style)`](@counter-style/system)
- [`time#s`](time#s)

T

- [`angle#turn`](angle#turn)
- [`tab-size`](tab-size)
- [`table-layout`](table-layout)
- [`:target`](:target)
- <span class="page-not-created">`target-counter()`</span>
- <span class="page-not-created">`target-counters()`</span>
- [`::target-text`](::target-text)
- <span class="page-not-created">`target-text()`</span>
- [`:target-within`](:target-within)
- [`text-align`](text-align)
- [`text-align-last`](text-align-last)
- [`text-combine-upright`](text-combine-upright)
- [`text-decoration`](text-decoration)
- [`text-decoration-color`](text-decoration-color)
- [`text-decoration-line`](text-decoration-line)
- [`text-decoration-skip`](text-decoration-skip)
- [`text-decoration-skip-ink`](text-decoration-skip-ink)
- [`text-decoration-style`](text-decoration-style)
- [`text-decoration-thickness`](text-decoration-thickness)
- [`text-emphasis`](text-emphasis)
- [`text-emphasis-color`](text-emphasis-color)
- [`text-emphasis-position`](text-emphasis-position)
- [`text-emphasis-style`](text-emphasis-style)
- [`text-indent`](text-indent)
- [`text-justify`](text-justify)
- [`text-orientation`](text-orientation)
- [`text-overflow`](text-overflow)
- [`text-rendering`](text-rendering)
- [`text-shadow`](text-shadow)
- [`text-size-adjust`](text-size-adjust)
- [`text-transform`](text-transform)
- [`text-underline-offset`](text-underline-offset)
- [`text-underline-position`](text-underline-position)
- [`<time>`](time)
- [`<time-percentage>`](time-percentage)
- [`<timing-function>`](easing-function)
- [`top`](top)
- [`@top-center`](@page#page-margin-box-type)
- [`touch-action`](touch-action)
- [`transform`](transform)
- [`transform-box`](transform-box)
- [`<transform-function>`](transform-function)
- [`transform-origin`](transform-origin)
- [`transform-style`](transform-style)
- [`transition`](transition)
- [`transition-delay`](transition-delay)
- [`transition-duration`](transition-duration)
- [`transition-property`](transition-property)
- [`transition-timing-function`](transition-timing-function)
- [`translate`](translate)
- [`translate()`](<transform-function/translate()>)
- [`translate3d()`](<transform-function/translate3d()>)
- [`translateX()`](transform-function/translatex)
- [`translateY()`](<transform-function/translatey()>)
- [`translateZ()`](<transform-function/translatez()>)

U

- [`unicode-bidi`](unicode-bidi)
- [`unicode-range (@font-face)`](@font-face/unicode-range)
- [`unset`](unset)
- [`<url>`](<url()>)
- [`url()`](<url()#the_url()_functional_notation>)
- [`:user-invalid`](:user-invalid)
- [`user-select`](user-select)
- [`:user-valid`](:user-valid)
- [`user-zoom (@viewport)`](@viewport)

V

- [`length#vh`](length#vh)
- [`length#vmax`](length#vmax)
- [`length#vmin`](length#vmin)
- [`length#vw`](length#vw)
- [`:valid`](:valid)
- [`var()`](<var()>)
- [`vertical-align`](vertical-align)
- [`@viewport`](@viewport)
- [`viewport-fit (@viewport)`](@viewport)
- [`visibility`](visibility)
- [`:visited`](:visited)

W

- [`:where`](:where)
- [`white-space`](white-space)
- [`widows`](widows)
- [`width`](width)
- [`width (@viewport)`](@viewport)
- [`will-change`](will-change)
- [`word-break`](word-break)
- [`word-spacing`](word-spacing)
- [`word-wrap`](overflow-wrap)
- [`writing-mode`](writing-mode)

X

- [`resolution#x`](resolution#x)

Z

- [`z-index`](z-index)
- [`zoom (@viewport)`](@viewport)

Others

- [`--*`](--*)

## Selectors

The following are the various [selectors](css_selectors), which allow styles to be conditional based on various features of elements within the DOM.

### Basic selectors

**Basic selectors** are fundamental selectors; these are the most basic selectors that are frequently combined to create other, more complex selectors.

- [Universal selector](universal_selectors) `*`, `ns|*`, `*|*`, `|*`
- [Type selector](type_selectors) `elementname`
- [Class selector](class_selectors) `.classname`
- [ID selector](id_selectors) `#idname`
- [Attribute selector](attribute_selectors) `[attr=value]`

### Grouping selectors

[Selector list](selector_list) `A, B`  
Specifies that both `A` and `B` elements are selected. This is a grouping method to select several matching elements.

### Combinators

Combinators are selectors that establish a relationship between two or more simple selectors, such as "`A` is a child of `B`" or "`A` is adjacent to `B`."

[Adjacent sibling combinator](adjacent_sibling_combinator) `A + B`  
Specifies that the elements selected by both `A` and `B` have the same parent and that the element selected by `B` immediately follows the element selected by `A` horizontally.

[General sibling combinator](general_sibling_combinator) `A ~ B`  
Specifies that the elements selected by both `A` and `B` share the same parent and that the element selected by `A` comes before—but not necessarily immediately before—the element selected by `B`.

[Child combinator](child_combinator) `A > B`  
Specifies that the element selected by `B` is the direct child of the element selected by `A`.

[Descendant combinator](descendant_combinator) `A B`  
Specifies that the element selected by `B` is a descendant of the element selected by `A`, but is not necessarily a direct child.

[Column combinator](column_combinator) `A || B` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Specifies that the element selected by `B` is located within the table column specified by `A`. Elements which span multiple columns are considered to be a member of all of those columns.

### Pseudo

[Pseudo classes](pseudo-classes) `:`  
Specifies a special state of the selected element(s).

[Pseudo elements](pseudo-elements) `::`  
Represents entities that are not included in HTML.

**See also:** [Selectors in the Selectors Level 4 specification](https://www.w3.org/TR/selectors/#overview).

## Concepts

### Syntax and semantics

- [CSS syntax](syntax)
- [At-rules](at-rule)
- [Cascade](cascade)
- [Comments](comments)
- [Descriptor](<https://developer.mozilla.org/en-US/docs/Glossary/Descriptor_(CSS)>)
- [Inheritance](inheritance)
- [Shorthand properties](shorthand_properties)
- [Specificity](specificity)
- [Value definition syntax](value_definition_syntax)
- [CSS unit and value types](css_values_and_units)
- [CSS functional notations](css_functions)

### Values

- [Actual value](actual_value)
- [Computed value](computed_value)
- [Initial value](initial_value)
- [Resolved value](resolved_value)
- [Specified value](specified_value)
- [Used value](used_value)

### Layout

- [Block formatting context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context)
- [Box model](css_box_model/introduction_to_the_css_box_model)
- [Containing block](containing_block)
- [Layout mode](layout_mode)
- [Margin collapsing](css_box_model/mastering_margin_collapsing)
- [Replaced elements](replaced_element)
- [Stacking context](css_positioning/understanding_z_index/the_stacking_context)
- [Visual formatting model](visual_formatting_model)

## DOM-CSS / CSSOM

### Major object types

- [`Document.styleSheets`](https://developer.mozilla.org/en-US/docs/Web/API/Document/styleSheets)
- `styleSheets[i].cssRules`
- `cssRules[i].cssText` <span style="white-space: nowrap;">(selector & style)</span>
- `cssRules[i].selectorText`
- [`HTMLElement.style`](https://developer.mozilla.org/en-US/docs/Web/API/ElementCSSInlineStyle/style)
- `HTMLElement.style.cssText` (just style)
- [`Element.className`](https://developer.mozilla.org/en-US/docs/Web/API/Element/className)
- [`Element.classList`](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)

### Important methods

- [`CSSStyleSheet.insertRule()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/insertRule)
- [`CSSStyleSheet.deleteRule()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/deleteRule)

## See also

- [Mozilla CSS extensions](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions) (prefixed with `-moz-`)
- [WebKit CSS extensions](https://developer.mozilla.org/en-US/docs/Web/CSS/WebKit_Extensions) (mostly prefixed with `-webkit-`)
- [Microsoft CSS extensions](https://developer.mozilla.org/en-US/docs/Web/CSS/Microsoft_Extensions) (prefixed with `-ms-`)

## External Links

- [CSS Indices (w3.org)](https://www.w3.org/TR/CSS/#indices)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Reference" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Reference</a>
