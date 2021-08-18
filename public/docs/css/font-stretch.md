# font-stretch

The `font-stretch` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property selects a normal, condensed, or expanded face from a font.

## Syntax

    /* Keyword values */
    font-stretch: ultra-condensed;
    font-stretch: extra-condensed;
    font-stretch: condensed;
    font-stretch: semi-condensed;
    font-stretch: normal;
    font-stretch: semi-expanded;
    font-stretch: expanded;
    font-stretch: extra-expanded;
    font-stretch: ultra-expanded;

    /* Percentage values */
    font-stretch: 50%;
    font-stretch: 100%;
    font-stretch: 200%;

    /* Global values */
    font-stretch: inherit;
    font-stretch: initial;
    font-stretch: unset;

This property may be specified as a single keyword value or a single [`<percentage>`](percentage) value.

### Values

`normal`  
Specifies a normal font face.

`semi-condensed`, `condensed`, `extra-condensed`, `ultra-condensed`  
Specifies a more condensed font face than normal, with `ultra-condensed` as the most condensed.

`semi-expanded`, `expanded`, `extra-expanded`, `ultra-expanded`  
Specifies a more expanded font face than normal, with `ultra-expanded` as the most expanded.

`<percentage>`  
A [`<percentage>`](percentage) value between 50% and 200% (inclusive). Negative values are not allowed for this property.

In earlier versions of the `font-stretch` specification, the property accepts only the nine keyword values.

**The [CSS Fonts Module Level 4](https://drafts.csswg.org/css-fonts-4/#propdef-font-stretch) spec** extends the syntax to accept a `<percentage>` value as well. This enables variable fonts to offer something more like a _continuum_ of character widths. For TrueType or OpenType variable fonts, the "`wdth`" variation is used to implement varying widths.

However, note that the `<percentage>` syntax is not yet supported by all browsers: check the [Browser compatibility](#browser_compatibility) table for details.

### Keyword to numeric mapping

The table below shows the mapping between keyword values and numeric percentages:

<table><thead><tr class="header"><th>Keyword</th><th>Percentage</th></tr></thead><tbody><tr class="odd"><td><code>ultra-condensed</code></td><td>50%</td></tr><tr class="even"><td><code>extra-condensed</code></td><td>62.5%</td></tr><tr class="odd"><td><code>condensed</code></td><td>75%</td></tr><tr class="even"><td><code>semi-condensed</code></td><td>87.5%</td></tr><tr class="odd"><td><code>normal</code></td><td>100%</td></tr><tr class="even"><td><code>semi-expanded</code></td><td>112.5%</td></tr><tr class="odd"><td><code>expanded</code></td><td>125%</td></tr><tr class="even"><td><code>extra-expanded</code></td><td>150%</td></tr><tr class="odd"><td><code>ultra-expanded</code></td><td>200%</td></tr></tbody></table>

## Description

Some font families offer additional faces in which the characters are narrower than the normal face (_condensed_ faces) or wider than the normal face (_expanded_ faces).

You can use `font-stretch` to select a condensed or expanded face from such fonts. If the font you are using does not offer condensed or expanded faces, this property has no effect.

### Font face selection

The face selected for a given value of `font-stretch` depends on the faces supported by the font in question. If the font does not provide a face that exactly matches the given value, then values less than 100% map to a narrower face, and values greater than or equal to 100% map to a wider face.

The table below demonstrates the effect of supplying various different percentage values of `font-stretch` on two different fonts:

<table><thead><tr class="header"><th></th><th>50%</th><th>62.5%</th><th>75%</th><th>87.5%</th><th>100%</th><th>112.5%</th><th>125%</th><th>150%</th><th>200%</th></tr></thead><tbody><tr class="odd"><td>Helvetica Neue</td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAAB0CAMAAAAy0NV2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAABsUExURf///+7u7sDAwPr6+vz8/A0NDYyMjAAAABYWFsjIyC4uLvPz8/7+/qCgoOXl5TMzM3p6etjY2JWVlX9/f97e3rGxserq6vf397e3t09PT2RkZGtrayMjIyoqKsvLy9HR0VlZWaioqDo6Oj09PYi5FrAAAAGjSURBVGje7ZfZeoIwEEaRCBMMOyhLKy59/3esYm1NCOn3McOVc+68OWb5ZzJ4HsMwDMMwDMMwDMMwDBXbui3zG+G+jknFh1LCLzLZkIlVCAbJlsbswxRZUJj3YMXHm1uYYcCaizkzyAPyBnezajjj7rIEBy3GvJEu9adAqBNwgkhJY560sYl+ec1HuqkUXpoRhaTSzOG4Ec29X2oWtiX6JCeSaov+euShOb5mRJH0pcoS9aAmiV5pa1fRMnP8ATZLYfs/RKqzLHh26HqSGnTB9JE/oiWy2yLVwWypd4JEfbU17Q0y1g91RqcuDLV8d3UqV1ObCVlRDXRqddQs+SmaMiwrGfFSI7sMTpSjr975SNUXIHkH/5/3nq+M6AmGVP0ef97G+1469HStPzNB+tK0cuSYakzt44sSd89fCqU2psnkVkb53y4umCE4Nr6Psl4vRcx9pu5JFa7NcnfoVleY/H06Z3fMVcatSz0QZhvMxKz0DRaiy/1wXGfN9yNRZ9vzMtC0wOldVoqqvapEK/kqpezd4hSOjSk4h1HjMQzDMMz78Q279C71noDkOAAAAABJRU5ErkJggg==" width="90" height="116" /></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAAB0CAMAAAAy0NV2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAABsUExURf///+7u7sDAwPr6+vz8/A0NDYyMjAAAABYWFsjIyC4uLvPz8/7+/qCgoOXl5TMzM3p6etjY2JWVlX9/f97e3rGxserq6vf397e3t09PT2RkZGtrayMjIyoqKsvLy9HR0VlZWaioqDo6Oj09PYi5FrAAAAGjSURBVGje7ZfZeoIwEEaRCBMMOyhLKy59/3esYm1NCOn3McOVc+68OWb5ZzJ4HsMwDMMwDMMwDMMwDBXbui3zG+G+jknFh1LCLzLZkIlVCAbJlsbswxRZUJj3YMXHm1uYYcCaizkzyAPyBnezajjj7rIEBy3GvJEu9adAqBNwgkhJY560sYl+ec1HuqkUXpoRhaTSzOG4Ec29X2oWtiX6JCeSaov+euShOb5mRJH0pcoS9aAmiV5pa1fRMnP8ATZLYfs/RKqzLHh26HqSGnTB9JE/oiWy2yLVwWypd4JEfbU17Q0y1g91RqcuDLV8d3UqV1ObCVlRDXRqddQs+SmaMiwrGfFSI7sMTpSjr975SNUXIHkH/5/3nq+M6AmGVP0ef97G+1469HStPzNB+tK0cuSYakzt44sSd89fCqU2psnkVkb53y4umCE4Nr6Psl4vRcx9pu5JFa7NcnfoVleY/H06Z3fMVcatSz0QZhvMxKz0DRaiy/1wXGfN9yNRZ9vzMtC0wOldVoqqvapEK/kqpezd4hSOjSk4h1HjMQzDMMz78Q279C71noDkOAAAAABJRU5ErkJggg==" width="90" height="116" /></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAAB0CAMAAAAy0NV2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAABsUExURf///+7u7sDAwPr6+vz8/A0NDYyMjAAAABYWFsjIyC4uLvPz8/7+/qCgoOXl5TMzM3p6etjY2JWVlX9/f97e3rGxserq6vf397e3t09PT2RkZGtrayMjIyoqKsvLy9HR0VlZWaioqDo6Oj09PYi5FrAAAAGjSURBVGje7ZfZeoIwEEaRCBMMOyhLKy59/3esYm1NCOn3McOVc+68OWb5ZzJ4HsMwDMMwDMMwDMMwDBXbui3zG+G+jknFh1LCLzLZkIlVCAbJlsbswxRZUJj3YMXHm1uYYcCaizkzyAPyBnezajjj7rIEBy3GvJEu9adAqBNwgkhJY560sYl+ec1HuqkUXpoRhaTSzOG4Ec29X2oWtiX6JCeSaov+euShOb5mRJH0pcoS9aAmiV5pa1fRMnP8ATZLYfs/RKqzLHh26HqSGnTB9JE/oiWy2yLVwWypd4JEfbU17Q0y1g91RqcuDLV8d3UqV1ObCVlRDXRqddQs+SmaMiwrGfFSI7sMTpSjr975SNUXIHkH/5/3nq+M6AmGVP0ef97G+1469HStPzNB+tK0cuSYakzt44sSd89fCqU2psnkVkb53y4umCE4Nr6Psl4vRcx9pu5JFa7NcnfoVleY/H06Z3fMVcatSz0QZhvMxKz0DRaiy/1wXGfN9yNRZ9vzMtC0wOldVoqqvapEK/kqpezd4hSOjSk4h1HjMQzDMMz78Q279C71noDkOAAAAABJRU5ErkJggg==" width="90" height="116" /></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAAB0CAMAAAAy0NV2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAABsUExURf///+7u7sDAwPr6+vz8/A0NDYyMjAAAABYWFsjIyC4uLvPz8/7+/qCgoOXl5TMzM3p6etjY2JWVlX9/f97e3rGxserq6vf397e3t09PT2RkZGtrayMjIyoqKsvLy9HR0VlZWaioqDo6Oj09PYi5FrAAAAGjSURBVGje7ZfZeoIwEEaRCBMMOyhLKy59/3esYm1NCOn3McOVc+68OWb5ZzJ4HsMwDMMwDMMwDMMwDBXbui3zG+G+jknFh1LCLzLZkIlVCAbJlsbswxRZUJj3YMXHm1uYYcCaizkzyAPyBnezajjj7rIEBy3GvJEu9adAqBNwgkhJY560sYl+ec1HuqkUXpoRhaTSzOG4Ec29X2oWtiX6JCeSaov+euShOb5mRJH0pcoS9aAmiV5pa1fRMnP8ATZLYfs/RKqzLHh26HqSGnTB9JE/oiWy2yLVwWypd4JEfbU17Q0y1g91RqcuDLV8d3UqV1ObCVlRDXRqddQs+SmaMiwrGfFSI7sMTpSjr975SNUXIHkH/5/3nq+M6AmGVP0ef97G+1469HStPzNB+tK0cuSYakzt44sSd89fCqU2psnkVkb53y4umCE4Nr6Psl4vRcx9pu5JFa7NcnfoVleY/H06Z3fMVcatSz0QZhvMxKz0DRaiy/1wXGfN9yNRZ9vzMtC0wOldVoqqvapEK/kqpezd4hSOjSk4h1HjMQzDMMz78Q279C71noDkOAAAAABJRU5ErkJggg==" width="90" height="116" /></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAAB0CAMAAAAy0NV2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAByUExURf////7+/vLy8uXl5TIyMvz8/L6+vgAAAMnJyRYWFoeHh+7u7m1tbSwsLCAgIEBAQLm5uaSkpLKysjs7Ow0NDff390xMTH9/f2NjY3h4eFZWVt/f3+vr64+Pj52dnaurq8TExGpqatnZ2VRUVNDQ0FlZWbVP+EcAAAGwSURBVGje7ZfrkoIwDEa5lVJUBEQugoiK7/+K62VXKRZkmzCzM5vzs84ca/yatIZBEARBEARBEARBEASBx8KL/CIrin1cmpjebZzyF4lfoolr3qeoUMye4AoihLJEXE3OoOaaD7EDumM+TAYyn/gYIcDMNqNqUc1Tjhu+fqBXH9T62w77quQt3ZpmM+0l2TaMMpeWNpoBLHtZe5y/vbR40lMfJElgfafG6a7Weuqj8oCYIfxI9vLhPtcdxW+BlFrYzw+W3cyU8POSMnUv9IDddOU4uan+zhr+L3L3h0ZqLHsd9aukzshZTxlcvUYcCNPUOrtm60lqsfi92lrNpu5MGGz1xFr/NfVxUq6Bu74rWk8Ng00CuYfAkTvfhSGqbeX8QqF3dfI6h8mFuv2Bm1J27RwnmLpRV+Qxdpc2RG0Fqm23zyFgoVWEF1cX61wVkgNDysit71/kd43Q/z8z/onNVlNdCT7bDTv6YA70q22eR80J5NlrjT4MGki2TTuY5wV2T+DQvkULblNWrjSfFxg9sHkvinCx+msoN9izizkYysPxPn2Tne9WBkEQBEH8N74A9osxzItuvhYAAAAASUVORK5CYII=" width="90" height="116" /></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAAB0CAMAAAAy0NV2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAByUExURf////7+/vLy8uXl5TIyMvz8/L6+vgAAAMnJyRYWFoeHh+7u7m1tbSwsLCAgIEBAQLm5uaSkpLKysjs7Ow0NDff390xMTH9/f2NjY3h4eFZWVt/f3+vr64+Pj52dnaurq8TExGpqatnZ2VRUVNDQ0FlZWbVP+EcAAAGwSURBVGje7ZfrkoIwDEa5lVJUBEQugoiK7/+K62VXKRZkmzCzM5vzs84ca/yatIZBEARBEARBEARBEASBx8KL/CIrin1cmpjebZzyF4lfoolr3qeoUMye4AoihLJEXE3OoOaaD7EDumM+TAYyn/gYIcDMNqNqUc1Tjhu+fqBXH9T62w77quQt3ZpmM+0l2TaMMpeWNpoBLHtZe5y/vbR40lMfJElgfafG6a7Weuqj8oCYIfxI9vLhPtcdxW+BlFrYzw+W3cyU8POSMnUv9IDddOU4uan+zhr+L3L3h0ZqLHsd9aukzshZTxlcvUYcCNPUOrtm60lqsfi92lrNpu5MGGz1xFr/NfVxUq6Bu74rWk8Ng00CuYfAkTvfhSGqbeX8QqF3dfI6h8mFuv2Bm1J27RwnmLpRV+Qxdpc2RG0Fqm23zyFgoVWEF1cX61wVkgNDysit71/kd43Q/z8z/onNVlNdCT7bDTv6YA70q22eR80J5NlrjT4MGki2TTuY5wV2T+DQvkULblNWrjSfFxg9sHkvinCx+msoN9izizkYysPxPn2Tne9WBkEQBEH8N74A9osxzItuvhYAAAAASUVORK5CYII=" width="90" height="116" /></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAAB0CAMAAAAy0NV2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAByUExURf////7+/vLy8uXl5TIyMvz8/L6+vgAAAMnJyRYWFoeHh+7u7m1tbSwsLCAgIEBAQLm5uaSkpLKysjs7Ow0NDff390xMTH9/f2NjY3h4eFZWVt/f3+vr64+Pj52dnaurq8TExGpqatnZ2VRUVNDQ0FlZWbVP+EcAAAGwSURBVGje7ZfrkoIwDEa5lVJUBEQugoiK7/+K62VXKRZkmzCzM5vzs84ca/yatIZBEARBEARBEARBEASBx8KL/CIrin1cmpjebZzyF4lfoolr3qeoUMye4AoihLJEXE3OoOaaD7EDumM+TAYyn/gYIcDMNqNqUc1Tjhu+fqBXH9T62w77quQt3ZpmM+0l2TaMMpeWNpoBLHtZe5y/vbR40lMfJElgfafG6a7Weuqj8oCYIfxI9vLhPtcdxW+BlFrYzw+W3cyU8POSMnUv9IDddOU4uan+zhr+L3L3h0ZqLHsd9aukzshZTxlcvUYcCNPUOrtm60lqsfi92lrNpu5MGGz1xFr/NfVxUq6Bu74rWk8Ng00CuYfAkTvfhSGqbeX8QqF3dfI6h8mFuv2Bm1J27RwnmLpRV+Qxdpc2RG0Fqm23zyFgoVWEF1cX61wVkgNDysit71/kd43Q/z8z/onNVlNdCT7bDTv6YA70q22eR80J5NlrjT4MGki2TTuY5wV2T+DQvkULblNWrjSfFxg9sHkvinCx+msoN9izizkYysPxPn2Tne9WBkEQBEH8N74A9osxzItuvhYAAAAASUVORK5CYII=" width="90" height="116" /></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAAB0CAMAAAAy0NV2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAByUExURf////7+/vLy8uXl5TIyMvz8/L6+vgAAAMnJyRYWFoeHh+7u7m1tbSwsLCAgIEBAQLm5uaSkpLKysjs7Ow0NDff390xMTH9/f2NjY3h4eFZWVt/f3+vr64+Pj52dnaurq8TExGpqatnZ2VRUVNDQ0FlZWbVP+EcAAAGwSURBVGje7ZfrkoIwDEa5lVJUBEQugoiK7/+K62VXKRZkmzCzM5vzs84ca/yatIZBEARBEARBEARBEASBx8KL/CIrin1cmpjebZzyF4lfoolr3qeoUMye4AoihLJEXE3OoOaaD7EDumM+TAYyn/gYIcDMNqNqUc1Tjhu+fqBXH9T62w77quQt3ZpmM+0l2TaMMpeWNpoBLHtZe5y/vbR40lMfJElgfafG6a7Weuqj8oCYIfxI9vLhPtcdxW+BlFrYzw+W3cyU8POSMnUv9IDddOU4uan+zhr+L3L3h0ZqLHsd9aukzshZTxlcvUYcCNPUOrtm60lqsfi92lrNpu5MGGz1xFr/NfVxUq6Bu74rWk8Ng00CuYfAkTvfhSGqbeX8QqF3dfI6h8mFuv2Bm1J27RwnmLpRV+Qxdpc2RG0Fqm23zyFgoVWEF1cX61wVkgNDysit71/kd43Q/z8z/onNVlNdCT7bDTv6YA70q22eR80J5NlrjT4MGki2TTuY5wV2T+DQvkULblNWrjSfFxg9sHkvinCx+msoN9izizkYysPxPn2Tne9WBkEQBEH8N74A9osxzItuvhYAAAAASUVORK5CYII=" width="90" height="116" /></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAAB0CAMAAAAy0NV2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAByUExURf////7+/vLy8uXl5TIyMvz8/L6+vgAAAMnJyRYWFoeHh+7u7m1tbSwsLCAgIEBAQLm5uaSkpLKysjs7Ow0NDff390xMTH9/f2NjY3h4eFZWVt/f3+vr64+Pj52dnaurq8TExGpqatnZ2VRUVNDQ0FlZWbVP+EcAAAGwSURBVGje7ZfrkoIwDEa5lVJUBEQugoiK7/+K62VXKRZkmzCzM5vzs84ca/yatIZBEARBEARBEARBEASBx8KL/CIrin1cmpjebZzyF4lfoolr3qeoUMye4AoihLJEXE3OoOaaD7EDumM+TAYyn/gYIcDMNqNqUc1Tjhu+fqBXH9T62w77quQt3ZpmM+0l2TaMMpeWNpoBLHtZe5y/vbR40lMfJElgfafG6a7Weuqj8oCYIfxI9vLhPtcdxW+BlFrYzw+W3cyU8POSMnUv9IDddOU4uan+zhr+L3L3h0ZqLHsd9aukzshZTxlcvUYcCNPUOrtm60lqsfi92lrNpu5MGGz1xFr/NfVxUq6Bu74rWk8Ng00CuYfAkTvfhSGqbeX8QqF3dfI6h8mFuv2Bm1J27RwnmLpRV+Qxdpc2RG0Fqm23zyFgoVWEF1cX61wVkgNDysit71/kd43Q/z8z/onNVlNdCT7bDTv6YA70q22eR80J5NlrjT4MGki2TTuY5wV2T+DQvkULblNWrjSfFxg9sHkvinCx+msoN9izizkYysPxPn2Tne9WBkEQBEH8N74A9osxzItuvhYAAAAASUVORK5CYII=" width="90" height="116" /></td></tr><tr class="even"><td>League Mono Variable</td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAAB0CAMAAAAy0NV2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAABsUExURf///+7u7sDAwPr6+vz8/A0NDYyMjAAAABYWFsjIyC4uLvPz8/7+/qCgoOXl5TMzM3p6etjY2JWVlX9/f97e3rGxserq6vf397e3t09PT2RkZGtrayMjIyoqKsvLy9HR0VlZWaioqDo6Oj09PYi5FrAAAAGjSURBVGje7ZfZeoIwEEaRCBMMOyhLKy59/3esYm1NCOn3McOVc+68OWb5ZzJ4HsMwDMMwDMMwDMMwDBXbui3zG+G+jknFh1LCLzLZkIlVCAbJlsbswxRZUJj3YMXHm1uYYcCaizkzyAPyBnezajjj7rIEBy3GvJEu9adAqBNwgkhJY560sYl+ec1HuqkUXpoRhaTSzOG4Ec29X2oWtiX6JCeSaov+euShOb5mRJH0pcoS9aAmiV5pa1fRMnP8ATZLYfs/RKqzLHh26HqSGnTB9JE/oiWy2yLVwWypd4JEfbU17Q0y1g91RqcuDLV8d3UqV1ObCVlRDXRqddQs+SmaMiwrGfFSI7sMTpSjr975SNUXIHkH/5/3nq+M6AmGVP0ef97G+1469HStPzNB+tK0cuSYakzt44sSd89fCqU2psnkVkb53y4umCE4Nr6Psl4vRcx9pu5JFa7NcnfoVleY/H06Z3fMVcatSz0QZhvMxKz0DRaiy/1wXGfN9yNRZ9vzMtC0wOldVoqqvapEK/kqpezd4hSOjSk4h1HjMQzDMMz78Q279C71noDkOAAAAABJRU5ErkJggg==" width="90" height="116" /></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAAB0CAMAAAAy0NV2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAByUExURf////7+/vLy8uXl5TIyMvz8/L6+vgAAAMnJyRYWFoeHh+7u7m1tbSwsLCAgIEBAQLm5uaSkpLKysjs7Ow0NDff390xMTH9/f2NjY3h4eFZWVt/f3+vr64+Pj52dnaurq8TExGpqatnZ2VRUVNDQ0FlZWbVP+EcAAAGwSURBVGje7ZfrkoIwDEa5lVJUBEQugoiK7/+K62VXKRZkmzCzM5vzs84ca/yatIZBEARBEARBEARBEASBx8KL/CIrin1cmpjebZzyF4lfoolr3qeoUMye4AoihLJEXE3OoOaaD7EDumM+TAYyn/gYIcDMNqNqUc1Tjhu+fqBXH9T62w77quQt3ZpmM+0l2TaMMpeWNpoBLHtZe5y/vbR40lMfJElgfafG6a7Weuqj8oCYIfxI9vLhPtcdxW+BlFrYzw+W3cyU8POSMnUv9IDddOU4uan+zhr+L3L3h0ZqLHsd9aukzshZTxlcvUYcCNPUOrtm60lqsfi92lrNpu5MGGz1xFr/NfVxUq6Bu74rWk8Ng00CuYfAkTvfhSGqbeX8QqF3dfI6h8mFuv2Bm1J27RwnmLpRV+Qxdpc2RG0Fqm23zyFgoVWEF1cX61wVkgNDysit71/kd43Q/z8z/onNVlNdCT7bDTv6YA70q22eR80J5NlrjT4MGki2TTuY5wV2T+DQvkULblNWrjSfFxg9sHkvinCx+msoN9izizkYysPxPn2Tne9WBkEQBEH8N74A9osxzItuvhYAAAAASUVORK5CYII=" width="90" height="116" /></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAAB0CAMAAAAy0NV2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAABsUExURQAAABYWFjAwMA0NDUJCQr+/v/X19f////7+/sjIyNTU1Hd3d/z8/N/f3yIiIkxMTNra2pSUlM/Pz1VVVefn54CAgGNjY8vLy7e3t52dne3t7aurq4aGhmxsbLCwsCkpKTs7O6Ojo8XFxV5eXoCLxFUAAAHoSURBVGje7dhtb4MgEADgE1pxirW+W9f3/f//uLk2LVDRethkze4+avIEDzgOQbwsgGiiiSaaaKKJJppoookmmmiiif6HtIybzTYqoyhtYjkjLesIlODleiZa7ldgRh7OQdePcBe71plOwRJe6EYHEdijdqLLARl47ECfYDAOPpoOYSRKNJ2M0RAi6eWoDFWAouXiQWLOM3mha3Mhn3+KR7HVH6Yo2ljS1XU5hJ76dOUjaP8A/cbSZd90dGCsvNN9h345ZOR31Bt9vgqlYGk1UE4fdaXRiSJoqZqYbHhMtfrdWka8eDKtpJozxjP1/Q4/jx29Nir/eXmLc9I/v9PpxfBe30ym9wbtWcuInEp/Pksnf5jm8DKawVuMunk217l82bo+SsfduM8+LJFN3jKxciIyBtj2sbfy6WuimbN114/GaE66AevxGrLMhQ4KsGWky1UVO4za6HDua+zaGJctmjbb1PJqB7cmJ/WxdGtswEV3OZKh8jF8L3H0412D5blnNms4ul3BE72qxNDKIWaPFDVqEeSj8lHi6PGUeAX6BrYeoTOBpodvSrwWDrSI7Tk5FsKJDvydrW2Swo0Wgaj7jrCowJcn7e+CMXK2aV3qtR7tcnvpT3m+bQrHo4D+mBFNNNFEE/1u9De0oAHWB78RHwAAAABJRU5ErkJggg==" width="90" height="116" /></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAAB0CAMAAAAy0NV2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAByUExURf///y4uLtvb2zk5Ob+/vxYWFvv7+wAAAMjIyP7+/nd3d+zs7M3NzTIyMmFhYU1NTSgoKGtra42NjSIiIufn5+Dg4LOzs/j4+PPz86ysrNLS0oeHh5WVlZycnKSkpLu7u1ZWVoCAgA0NDT8/P1xcXMXFxfS9MRYAAAHPSURBVGje7ZjbkoIwDIY5CAXkoOUoyknd93/FVdnBtlCQtszuzuS78IIOv2mSJimaBgAAAAAAAAAAAAAAoJS9c8Leg65qUluhroFjROKVrhrh3Q2NsDIF4v4BTWI5ksIuRlzOUobndzRDKBHPPEKzHIXtdkO0wEVUukKLCMbSWFZGh3wbdzw5iUg7E0LB2GyBLHHZ7LjWe02zk0re26ynw+JnobjLJuCFVjbfG89N6sDvV/vDpKV97oaatdIJrXyjouWRS3itdDOXYz65FK11tkdX0IRaLMjOEBfCqXcNgqC1+YFg/naRYmgA19fvjkbnRfiTcjq8rKs+62+rdc4JF66s79Ttpc3fka62kw7dzaQj+z9Kr3QIm3xzYNEj07ep0uGTrixPR6IhBkGncp7GvB4jzxftT0PlLcCip1J6NYtLiemXHnDo5po+O3kirJ3RHvHIHfWZeS7UeAThIZLG0L5qweie2RvG7jU6puRzq1Fi9rNatC37MBCKZ40+QuRqYN/QZmNwupXR4xFqilg0A09LypaygzOyOZGoJc6ccpfL1SnubUn6lq5p5eSdV8m3hUfVYA898nxXVfnOy/rYd3W97TKl33EAAAAA4M/zDaMnNnfdB7yWAAAAAElFTkSuQmCC" width="90" height="116" /></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAAB0CAMAAAAy0NV2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAABvUExURf///+bm5hYWFvPz8y0tLQ0NDf7+/gAAAMjIyL6+vpWVlfv7+4KCgqurqyIiIvj4+G1tbY6OjmBgYJ+fn3d3d+vr67e3t1ZWVt/f38/PzzIyMtbW1kxMTLGxsVFRUcXFxdnZ2Xt7ezs7O2RkZO7u7n99KHIAAAHCSURBVGje7ZjZlsIgDEC7Qvd9s7bW7f+/0ZmjR4VWWgI+zJncR9ErDUmIGgaCIAiCIAiCIAiCIIhe7GNTRtWpqqLA70J9XjM+UIZs0mP3CjrHLW11sUM/UKrtPD3RzySdSpAdKsLdgc2dRVeAus1VM7VMWJx7us4ZdJYR3UIAMO83mSEhIYellFh4LZdWTzNHdEwNIzTjhNv2VXXTxfPBw5JdiWUTjzO375kwMkuDZJLEosMiTPK4cvVOCmGK2Uy8fSkz+1lq1dwbcniONOymK359xwSbAEPd97018evX96dKpG6FikvpyWcZ4QWZiepvhqegdvV17Vfu3aXiy4aWMlOHI6WWaazpn1R/MSCSxxh8L6+lmkjOfrbZeSI6YA9xfnoIbNrYdJ2POid19uBaotGdrXSJqIWOqcQXz1+/V0VVAyOSiFL38cVBCnLzE1/+0pDnIOKOkEMwZ8NdeQ9AzYxPlg9w5/Oqc9q2nc3cw141/wRU0lHxtqoBBRVsM5801M0yQ2h8yX0G/uol+Zq5SMG9pBGbY5W+VV8+i7NatXcXy+LLUcf/IUHCew9xrat/m000WI9qj+K9bSAIgiDIv+EGUZc4CMz/hD8AAAAASUVORK5CYII=" width="90" height="116" /></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAAB0CAMAAAAy0NV2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAB7UExURf///zIyMmxsbOjo6P7+/u/v7xYWFgAAAMrKyr6+vlVVVfv7+97e3vf39yMjIw0NDdPT05WVlS0tLbCwsNra2n5+fpycnKOjo0pKSvLy8rW1tV5eXnl5ecjIyHV1dRwcHGNjY4KCgjk5OdDQ0Kenp4eHh4+Pj6qqqkBAQNv3V28AAAHWSURBVGje7ZjZloIwDECBFgoFRWRHcMNl/v8LZzzOOUqpkJbO0+S+qteYJmnQshAEQRAEQRAEQRAEQUwTku6enNpT256KIFsZ87qNw4bw1DUh9ndMhrNZKg7W7BN8kZxUbIo81A+ZzXDWTXnJZjkQLXPBAKx14m4YiEo93xEDkqia6RdUHUeK6pSBcaiSuR53itM9Tix0A7HrWbas7vK3KiOCPFcadGfBXE7VpadQ3DQTzHvxHbfBy6lC1InQc6O+oJXmQYqVd5GM2kFLwu8G4g2DriWnYeuV9ub1KfuHq+w9+/cvD8DquzCCumCMp9fsr1O0YQ3Jwed4FNSeObWjqoaXiKDezibEc1Gtp6ZChcQGo1aua7hauL1ufTeDH2qM69i2WWNwm3aHN+ORmlPTHWAd0NzfhWTLwvbZTUsu3AWSbD+OI041MkXFXaOXXxYHX13di5V7ef/1q9eywCNlNx+tdkn0LN66vw4XHNU1WLqoVpxzyewuFPfgEr5PMi9aUtvT95di2PUWalZ+6KBk/SfpeDYOKG4v0xklK0C+z3qPd9S6zJkL/alInCnxniyasFH+SXwli8d33fDxI13eGfrDpe7L/e+DwJa3ZUcsBEEQBPkffANELz6XEW05CQAAAABJRU5ErkJggg==" width="90" height="116" /></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAAB0CAMAAAAy0NV2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAB4UExURQAAAPb29u7u7oeHh/v7+xYWFv7+/v///8jIyL6+vszMzDMzM1VVVWxsbEJCQrKysqurq3d3dysrKyIiIo2NjeXl5d3d3ZWVlUtLS9PT0/Pz89jY2H5+fjo6OqWlpQ0NDeHh4WBgYLu7u8TExKCgoJubm1tbW2JiYqHuGvcAAAIMSURBVGje7djbeoIwDADgUko5OuQgclTmae//hpufbkIpkqBebEtuLb/QkjSF2S8LRjTRRBNNNNFEE0000UQTTTTRRP9jmle7TVpHdRSZh11VPos29qbF+pEfsifQ3oJpww+Nh2gRJmw8jsZ82rsHf8XWnUnLlE1GLebQZc4AEQg0LXnMQJELLF36DBgfAkfLdwaOI45eMkRUGHqFkSFLye5NRxC25wwR3EvVtGcOnC4GsLnq5qgXY9+SHzqaui1p9n/3oDRXn3g/HLvuDYig9E6RU93gujsiMYC0Uka118myV7oKGF0qi7TTj+4Vrw2Mzm5XxL7vNyPLn3XphQTR7k2+LKKri33vJWkEiL4l+Rs4IS0OoiOFbiB2AaIXCm1BaO9X0us/TJuvo+e81/oSNqAdpc4XDiAyEN12m0bfqp/YXwsflcOo7imFrZAh8HQBqg9GYzloWjTTZU2W50FBi22C1d4pWQ3GVtf9yyxxtLqFse2yJ0je2QeWEtXzhcOciLzrtIg2PPXna4+h9Y3qNg+CQNccBxmctnmCaiihO/rlhISStxWC1k33eLg2hpaI7n2JPdy5UDnEH0kz0CHMKmw8bQvAoXSNPtx93/jESczkyBrSjbYen4oNx1Y+tXq6kS4DUZ9Exr/iiCw0T9cUj/PF0c2MebvM6B8IQ4jHNjD6GEc00UQTTfTz4xNzp/qdn0av2QAAAABJRU5ErkJggg==" width="90" height="116" /></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAAB0CAMAAAAy0NV2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAB1UExURf////39/Q0NDS8vL/Ly8hcXF9vb2wAAAMjIyL6+vvn5+aOjo4CAgKmpqTg4OJSUlM7Ozp2dneLi4uzs7IeHh9XV1VZWVufn58vLyyIiImlpaVxcXK6urkdHR21tbY6Ojnh4eLq6ulBQUGJiYrW1tUBAQMLCwqUE5ooAAAHzSURBVGje7ZjZkoIwEEVFCEEIshk2cV/+/xPHscpRAiTdgC9TfV4NtyJ9b6fDYkEQBEEQBEEQBEEQBPElrEyewkgIcTyKKFi5zkyyblhzFVt4k+Xlhg+x96zxuk7AuI5lMnLrfsLNJGN2Lm0OoXLRxYs4lCvyZWw5nAilfOMYNoi3seU4ErD0hmPxgMqrQYVB01Qwg2dVz7O7JM78Zxkc9yS6SRIgadF5joWZUgzZWQSxd9E1gN+zLM3bi3JALDtZCQcWhu1l0mzpNdhYHtLcsdo6NX+0aZnER3pa66p2tEyFtM4fLrZt1mhXXz+lA1P3V1JxWGm4tyx4MXjEfR8h2LCbEqlKI1ogy/TSJ0XaRmy71EuHivQaIR1/T9pgkWCCdAQN4+zS7vek07c0wxr7YGh8itu80gOTGpL+MZUuHz0kXcyH0uCPM0qr59dJX/UMM+zViIyVj5wgRtUSPr4888VK+LZvwBna3b0adQHVjrvtsum8Ur+8fIbFB2qLnjicw79rl+XIRi0IuwNH4IF0L3f5g4Efc1gCCnTGf2lg95gRyqwYW0qjMrglSPYt5ceUnWOUc2dKo9IRYi+m2R54BIy5TrtmcRaM/cSQBZVO+FhaUzp4Gpz7S5dIf/r54MjroX4l3N7VmyYu/AVBEARB/GN+AG2xROhlV43AAAAAAElFTkSuQmCC" width="90" height="116" /></td><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAAB0CAMAAAAy0NV2AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAB+UExURQAAAPz8/PX19ampqRYWFi0tLTIyMv///8jIyL6+vu7u7unp6f7+/vj4+A0NDdra2uTk5NbW1t/f31VVVW1tbXV1dUhISHl5eZWVldDQ0GFhYYmJiSEhIY+Pj8vLy/Ly8pubm8PDw4CAgLq6urOzs62trWlpaU5OTjk5OaKiosCXg4UAAAJWSURBVGje7dhZk6IwEADgXApyCEG5RUBwR///H5xDa5cjgRB0Hra6yzedr3qSdJIOMt4WCGiggQYaaKCBBhpooIEGGmiggQb6GcTnO1rllzj++uQJ3XEbr6cJp+ENCeJQmJY+jb37B5qKbeVp0TxnaD5YZS+kcXtCqnH0ltANQ0viaKvSfoSWxt1Roq9IIyJ7nnb/IK3Ym3O0vUG60U7T9gmhV9hjupzJeeZrU05jSfHtj9QMLPexb2Bi8ybJhPXjS+lE9Pu4FtYb9tvxhN+whA4E+VJiGI6ssko6LK1cQofjMivndrB2gHtCepw0Vdh13byfjCOi86Fcqx0UbW8EAwFNNtKlNBO0+1fJmHbS7vrdblmifBA63TV7csdZ3wdJVzvVqHv/Lx/TnVW6XVHtjxHp0e52QN806QMe0t1Z/KGZJn0qR1kPaO3NlVlvo9H5F2nyPtrJ+vSevYw2ihet658Nok/vBhOdmnpRj1aIYbHeHvLcwl5zvz4Klv6L6HR40FmqEI6badoZntIsVZP510LNpi9mfDTZOZmH/edAUmfq9nQRnOgzI87/ndVRMEETUQkeG1vCWueiX1cJll/MfHEJsvCa2m5n2kr/TGPBb0+p/DrJJ7ui6PAd0VSxXoj0EpyilfEoNeHV3WPr6ALLGw4rWiPTyV7GqbRhls41d4Fm4iFRaEl3Go3Hgas10rhZdoLtC1+5R3eMNFSGs9pd+GhBagWdXcxS6z0Ee1Teo+6zRPIoovqKg630WoQff+t7E2VxcTWD8jFw8GIGNNBAAw30f0N/AmuS8I34oxFpAAAAAElFTkSuQmCC" width="90" height="116" /></td></tr></tbody></table>

- **Helvetica Neue**, which is installed by default on macOS, has a single condensed face in addition to the normal face. All values of `font-stretch` less than 100% select the condensed face, while all other values select the normal face.
- **[League Mono Variable](https://tylerfinck.com/leaguemonovariable/)** is a variable font that offers something like a continuous range of widths for different percentage values of `font-stretch`.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="#Interpolation">font stretch</a></td></tr></tbody></table>

## Formal syntax

    <font-stretch-absolute>where
    <font-stretch-absolute> = normal | ultra-condensed | extra-condensed | condensed | semi-condensed | semi-expanded | expanded | extra-expanded | ultra-expanded | <percentage>

## Examples

### Setting font stretch percentages

**Note:** This example will only work in browsers that support `<percentage>` values.

#### HTML

    <div class="container">
        <p class="condensed">an elephantine lizard</p>
        <p class="normal">an elephantine lizard</p>
        <p class="expanded">an elephantine lizard</p>
    </div>

#### CSS

    /*
    This example uses the League Mono Variable font, developed by
    Tyler Finck (https://www.tylerfinck.com/) and used here under
    the terms of the SIL Open Font License, Version 1.1:
    http://scripts.sil.org/cms/scripts/page.php?item_id=OFL_web
    */

    @font-face {
      src: url('https://mdn.mozillademos.org/files/16014/LeagueMonoVariable.ttf');
      font-family:'LeagueMonoVariable';
      font-style: normal;
      font-stretch: 1% 500%; /* Required by Chrome */
    }

    .container {
      border: 10px solid #f5f9fa;
      padding: 0 1rem;
      font: 1.5rem 'LeagueMonoVariable', sans-serif;
    }

    .condensed {
      font-stretch: 50%;
    }

    .normal {
      font-stretch: 100%;
    }

    .expanded {
      font-stretch: 200%;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-4/#propdef-font-stretch">CSS Fonts Module Level 4<br />
<span class="small">The definition of 'font-stretch' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds the <code>&lt;percentage&gt;</code> syntax for variable fonts.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-fonts-3/#propdef-font-stretch">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'font-stretch' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

**Note:** The `font-stretch` property was initially defined in CSS 2, but dropped in CSS 2.1 due to the lack of browser implementation. It was brought back in CSS 3.

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

`font-stretch`

60

A `font-stretch` definition must be added to the `@font-face` before this property will function.

12

9

9

47

A `font-stretch` definition must be added to the `@font-face` before this property will function.

11

60

A `font-stretch` definition must be added to the `@font-face` before this property will function.

60

A `font-stretch` definition must be added to the `@font-face` before this property will function.

9

44

A `font-stretch` definition must be added to the `@font-face` before this property will function.

11

8.0

A `font-stretch` definition must be added to the `@font-face` before this property will function.

`percentage`

62

18

61

No

49

11.1

62

62

61

46

11.3

8.0

## See also

- [`font-style`](font-style)
- [`font-weight`](font-weight)
- [Fundamental text and font styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-stretch" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/font-stretch</a>
