# Mastering margin collapsing

The [top](../margin-top) and [bottom](../margin-bottom) margins of blocks are sometimes combined (collapsed) into a single margin whose size is the largest of the individual margins (or just one of them, if they are equal), a behavior known as **margin collapsing**. Note that the margins of [floating](../float) and [absolutely positioned](../position#absolute) elements never collapse.

Margin collapsing occurs in three basic cases:

Adjacent siblings  
The margins of adjacent siblings are collapsed (except when the latter sibling needs to be [cleared](../clear) past floats).

No content separating parent and descendants  
If there is no border, padding, inline part, [block formatting context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context) created, or _[clearance](../clear)_ to separate the [`margin-top`](../margin-top) of a block from the [`margin-top`](../margin-top) of one or more of its descendant blocks; or no border, padding, inline content, [`height`](../height), [`min-height`](../min-height), or [`max-height`](../max-height) to separate the [`margin-bottom`](../margin-bottom) of a block from the [`margin-bottom`](../margin-bottom) of one or more of its descendant blocks, then those margins collapse. The collapsed margin ends up outside the parent.

Empty blocks  
If there is no border, padding, inline content, [`height`](../height), or [`min-height`](../min-height) to separate a block's [`margin-top`](../margin-top) from its [`margin-bottom`](../margin-bottom), then its top and bottom margins collapse.

Some things to note:

- More complex margin collapsing (of more than two margins) occurs when the above cases are combined.
- These rules apply even to margins that are zero, so the margin of a descendant ends up outside its parent (according to the rules above) whether or not the parent's margin is zero.
- When negative margins are involved, the size of the collapsed margin is the sum of the largest positive margin and the smallest (most negative) negative margin.
- When all margins are negative, the size of the collapsed margin is the smallest (most negative) margin. This applies to both adjacent elements and nested elements.

## Examples

### HTML

    <p>The bottom margin of this paragraph is collapsed …</p>
    <p>… with the top margin of this paragraph, yielding a margin of <code>1.2rem</code> in between.</p>

    <div>This parent element contains two paragraphs!
      <p>This paragraph has a <code>.4rem</code> margin between it and the text above.</p>
      <p>My bottom margin collapses with my parent, yielding a bottom margin of <code>2rem</code>.</p>
    </div>

    <p>I am <code>2rem</code> below the element above.</p>

### CSS

    div {
      margin: 2rem 0;
      background: lavender;
    }

    p {
      margin: .4rem 0 1.2rem 0;
      background: yellow;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/box.html#collapsing-margins">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'margin collapsing' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## See also

- CSS Key Concepts: [CSS syntax](../syntax), [at-rule](../at-rule), [comments](../comments), [specificity](../specificity) and [inheritance](../inheritance), the [box](introduction_to_the_css_box_model), [layout modes](../layout_mode) and [visual formatting models](../visual_formatting_model), and [margin collapsing](mastering_margin_collapsing), or the [initial](../initial_value), [computed](../computed_value), [resolved](../resolved_value), [specified](../specified_value), [used](../used_value), and [actual](../actual_value) values. Definitions of [value syntax](../value_definition_syntax), [shorthand properties](../shorthand_properties) and [replaced elements](../replaced_element).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing</a>
