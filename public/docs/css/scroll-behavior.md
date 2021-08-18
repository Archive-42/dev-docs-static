# scroll-behavior

The `scroll-behavior` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the behavior for a scrolling box when scrolling is triggered by the navigation or CSSOM scrolling APIs.

Note that any other scrolls, such as those performed by the user, are not affected by this property. When this property is specified on the root element, it applies to the viewport instead. This property specified on the `body` element will _not_ propagate to the viewport.

User agents are allowed to ignore this property.

## Syntax

    /* Keyword values */
    scroll-behavior: auto;
    scroll-behavior: smooth;

    /* Global values */
    scroll-behavior: inherit;
    scroll-behavior: initial;
    scroll-behavior: unset;

The `scroll-behavior` property is specified as one of the keyword values listed below.

### Values

`auto`  
The scrolling box scrolls instantly.

`smooth`  
The scrolling box scrolls in a smooth fashion using a user-agent-defined timing function over a user-agent-defined period of time. User agents should follow platform conventions, if any.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>scrolling boxes</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | smooth

## Examples

### Setting smooth scroll behavior

#### HTML

    <nav>
      <a href="#page-1">1</a>
      <a href="#page-2">2</a>
      <a href="#page-3">3</a>
    </nav>
    <div class="scroll-container">
      <div class="scroll-page" id="page-1">1</div>
      <div class="scroll-page" id="page-2">2</div>
      <div class="scroll-page" id="page-3">3</div>
    </div>

#### CSS

    a {
      display: inline-block;
      width: 50px;
      text-decoration: none;
    }
    nav, .scroll-container {
      display: block;
      margin: 0 auto;
      text-align: center;
    }
    nav {
      width: 339px;
      padding: 5px;
      border: 1px solid black;
    }
    .scroll-container {
      width: 350px;
      height: 200px;
      overflow-y: scroll;
      scroll-behavior: smooth;
    }
    .scroll-page {
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100%;
      font-size: 5em;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#propdef-scroll-behavior">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'scroll-behavior' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial specification</td></tr></tbody></table>

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

`scroll-behavior`

61

79

36

No

48

14

61

61

36

45

14

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-behavior</a>
