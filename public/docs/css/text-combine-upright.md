# text-combine-upright

The `text-combine-upright` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the combination of characters into the space of a single character. If the combined text is wider than 1em, the user agent must fit the contents within 1em. The resulting composition is treated as a single upright glyph for layout and decoration. This property only has an effect in vertical writing modes.

This is used to produce an effect that is known as tate-chū-yoko (縦中横) in Japanese, or as 直書橫向 in Chinese.

    /* Keyword values */
    text-combine-upright: none;
    text-combine-upright: all;

    /* Digits values */
    text-combine-upright: digits;     /* fits 2 consecutive digits horizontally inside vertical text */
    text-combine-upright: digits 4;   /* fits up to 4 consecutive digits horizontally inside vertical text */

    /* Global values */
    text-combine-upright: inherit;
    text-combine-upright: initial;
    text-combine-upright: unset;

## Syntax

### Values

`none`  
There is no special processing.

`all`  
Attempts to typeset all consecutive characters within the box horizontally, such that they take up the space of a single character within the vertical line of the box.

`digits <integer>?`  
Attempts to display a sequence of consecutive ASCII digits (U+0030–U+0039) that has as many or fewer characters than the specified integer, such that it takes up the space of a single character within the vertical line box. If the integer is omitted, it computes to 2. Integers outside the range of 2-4 are invalid.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>non-replaced inline elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>specified keyword, plus integer if 'digits'</td></tr><tr class="odd"><td>Animation type</td><td>Not animatable</td></tr></tbody></table>

## Formal syntax

    none | all | [ digits <integer>? ]

## Examples

### Digits

The digits value requires less markup than the all value when digits are being combined, but it is currently not very widely supported by browsers.

#### HTML

    <p lang="ja" class="exampleText">平成20年4月16日に</p>

#### CSS

    .exampleText {
      writing-mode: vertical-lr;
      text-combine-upright: digits 2;
      font: 36px serif;
    }

#### Results

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAHkAAAFGCAMAAAB5f8C3AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAJcEhZcwAACxMAAAsTAQCanBgAAABdUExURf///z+37O/v7w8PD7+/vz8/P39/fwAAAH/P8r/n+N/f3y8vL19fX8/Pz5+fnx8fH29vb4+Pj6+vr09PTyeu6gIoO2LC7ZfR6kVtfx9HWYuzxQB3rBSMwl+Hmdfw+3uei9wAABEYSURBVHja7JyHcuSoFkDVxDEiiglv0/v/z1yiAOVW4/Wuy6qamXYP5khwuYkrhv8/Lly/hne43r71afNfIAv2QWQBobzQK9fgLjk/2uJikFLKT3vllI5iow0gGFtzTCYKl8vhxupHbDKZcLJ1OTClbmxWZIwc3ejrA4ApRZtzKCQq10ipqX5ELJNlRon4AT9FnuInKfalp9wfqNsgO981IlfIjLO6z/g7w5g/JDJgDTlNobUgt2Hc1H1eemYCyYrM3PyNrCaPGqzvD1IYxujtJyn/HUUeDQjLszFWFINFn9pLzlSPtqAQLcnSC5jv/u0HruQOxSXD2OnsIvd8oO3TCTlezLOOkLqV+wAN2Hrmq5dyS7fp0z2MAgsyoFmwcitG8834edakUhJhTVL3RxyTTe4096koXMu2W7wQ1K3cF3pbthOfnOsxmh469SkrcCFPNMl0asXySA2r9ZwF4ny487SmPlUSrpbsh7tuxak9sRgXyCSNX+zTQLFph9z/2tKKRbW+SQZBt5Er2tOYIjtAJfC06NWZL1HImO9bSRZW1zQ8pT3JIEFeRju2KrSakviITVv19FW0U1QTXo3tkJOaAGrTVk2YM3aowiStjaK3kqr67JZRICNSmyZvq3j+jH0rvZpnPAgODD/UX1esJMONVfaKp7XTS7K3VU6wbQf7fNJqh4z/eXLCfgCZjQqrcZRPkWUPMnhpVR2SSW9/uxc5Wkk4PmWoOz4zeGJV0UtkenW08YeR5QeQz/X2O5Gv6O1WAdDZhz8gg3Py83pbZff3jNxdb29G5d+XSZE//vhz8c33l/V2r2zF03obgE7k5/U2HPUETuf5Qhs31Ug8Q7ZOeJS0RBz26ryhkYjDNtJ5MXp8gk1CPDWW4GGT7ANN4uISKw7W8/z3tUuGKAI1y3pNJqGV+3uOCLZW1XN6G8X4BfuHBrv5sNgKwDmgu0cGHKzIyLsmY50Pq5MVuRXxZLmdDwsKCZ3osBESUKnPcJ9OfHjWkbHXqlEmA2uZiEH/iiysHCQ/WVxOXuDs6s+fR+/BB3Ts1VJY3H2Hix8mHw642b7nDZGSmPBmaNzWEl7qZ8e+/hwitx2yviRVszu0TZbt/cEzbRPDoGNt0pDxHvm41Wo9jzEMIvLEKDd9+tus3YltMmi08831nPsEUdyC6XUitOi1JtvYCqhpz+uNdy6ukSevt0jUXiKnmFdk4NcvielR5yJg9orFSJLqFogFKKpsnwbKOYuWbP33Mq43r2XD5GxYDEuUxufPPKZ4XDEWlxWvbMZMhjmeF2nSjTdsYFPCrJ9kcHGeY5ymgvDAytNqnznGF3FZjbNhuemHNWTuVbasFcqKjNISYDkneNv3bPqc/Dg3wewW2fgn16scYOUBMkc+200Qydgl9eAG2tHVcj2DkoVjQQcobyXZHlm427dnDiAq+b+cV2386VmT1K3cFNtinm9ajCkNLYx9+jiD4mGPPMZWIacOwXEOkJBTWyVStDR7gaxKWcVeTVZuqZUqHhPYzXuexFU8Gp60kp2yn7PqjDRWEtRmihdZMHfjZ0wtcj4qTpIaNr/iBJqKjOkoUDGWQX1FYfAJ0HtkP80meCBTBI8wzbyqyIpqUPwUEVKTcWg4uSlhKIwaTll9D/bK26Nl5YcxP/dhr9KLlQdLHl0wRu+SdXg+kdP0oTcvudaZkEKW4b5MdLEDOAiEiyLsbbKKelIyHxPMMxzGNU586NUGcQfKm06U9sfS6N8lo7Jz4BxJjKrkdt4F++Y1GGk8RpZiVZqm+46EzTt4CEOO6lxaSm+HXsnchzOm8+05Y0ij3tnRJIqg/UdOYKRXjaSNu+6uV5B3DyeMTbPnh7xGGXc0ifM98a2du6IZBcgezobBMeZgtA8e+k6eZH19/6eqOh6neZJLFuM9yNcsxnuQn8+4fgIycxEVON9zZxMhpvHKgSREvEIekeHsrJSFcRoCdVU2MA2E7ps2cmHctYHRq4tk4LfMLNrzeu2Z1yugZUkH69lLUSF4glXkov2G4MTjVmUgC0UJmlT4rTuevoDJj/PG12Rrkbb+1Zx94ckB8XaSBbJzenX8Nb0X3ZxYjNnP1MmZdF2O2SnNeRIyxxzYG4hH+BBvmfj7XGfiOBk11ye5dDF7v+Ghdc6b+zx28ithcfe8//VIsUgKFNYWgwVNchhKmuJco+QKFD8/Vum4XqeSxfetyKPezXNihm54BoRmBzr0ieOjsyxpfpBdr4TOOZnQ6hHGqtwfv6G3WXlmE71dPd9KAAYLKAvZ35h9hMalFbyjtyfMS82QH0BcUk6EZukZ57HVcbRte3+/b4/2tR0UkTzaKqoKc5rqY7ImDDmDh5/csXLZ/npFb+Mo2mCbXMuFX1WLVv/bHO1r+1UmSTZa9Nl6d17deE0iFq1+25QwjC6ONR9OyWN09R/LVj9ujzaY67QOyTql8TuSi+wekWUs7rxMFudkXirtlhLGC9nNSHKfV/P8Y3PPnYtzRVbt7+zKtovj+OwZnMj25URJvQ06Fk1iQkydyC5+k8UngWU9T5tk4dycM29IwAKOqbhaO831q7ZKkT3C6j/SYZygcTpJS4GxgKWNKmku0/LGMedJZHGfHgFXkVcWQ1/IPuqSWwLKNLvLMZyO2rN6Yq4fYf2LOdlt73hDqCTd3EyiaBvNLGypPsyF7NU+3vQIVnma7bNcZdb1ed5zzB4LM2n3BKU8Y3Y7gjc0V396sWOP8I/OdlatvV43xSM6nOeUG0gXztPL0ipnkcyozQXbvnbN+2FO66l8Jxs1cUAOJ7KtGjLJo562CKfk9fKmFQ8eIIqT4u7A3smToKbLuSrbUkx0qShmbSsZ/W3pFZ9rurk7eG4pmvq+YtQQx9jMWXPR1ApilmKMkEqB5H6u94WIjuWbffvX5Aw6kf9NeZKh5zObS72C/mRElTzvle01eoHsTbFiZ736TR3ZmexzBqQdy41sBaeUQtGVzNaFV6SpwZ8DjMUrCCIkHF4g83ajKPudi91OWW8UZRUffMfbZP/ICi/rqZNDVnoNCZnm4i9k1vMjk+wM4N059O72Zm3FfbIovCNyeUlj1eouGUcX4IRMShlTL7KZnbkjMiuOfi+y61IOqz7ZcrcTV5vhncjYgRFY9AnUovbL1IHITM45mFvk4MKTXApVeYGwrq0IgQjJWi63Qjn2vbdfhWIXsKmVonPBRvS3Rxy27lK9VK6V8v6jvfm+JIvacK7N2ZEwTlIrtV7P7CXteUJO76Xtt3o38mmrL/LLZC2vkBnoTiZN7eNeq5hxuEEGaK9Pmbe+D8lgvF37qJq3jr0GaX6e0i5wfud4uZ7D3jcUHWIMul2BKKfGFfFeW/Ma8utkRPdqH5fOU++46hoZfZG7kOWHkcklMnknMvswMrpERp3JZrd++3hkOuiwjVqVdZ7kz9WLN98/ySkhX+TPTZ4I+xgyu6YlxqZVFzK+RDa0O3m6pBkB7E72XV4gW9qdrC+Rq6reXmRBzRWywt3JmKALZDKi3mSpwAUyg6g3GcBpuEC2fOhN5na4QJ4g6E1GPhN4SgY+t96ZPOa3eA7JBA+9yWYcLpBZyFV1JYNYXnFGxmToTU6lcyfkSYHeZJT2CY7JQKGhN1lVNTT7ZG2H3mQDq1PQeFNHV/Uqcga+I1nmxIhPfPjUyWavhC6unp7B4WiznBjxFs1UW+XvTt5t9UW+7wFOH0Fm4c0OcEbWi0MzXiajZWXJtk8Sjz6kugQjL5NLeQk4IJfyEvEVS3Ynf9p6kg8jm0X9wPaqAu9AxrQ6a9PvTpCtXrFmrWkFr5Nts4ERdjq3yNUBccFUQvEyuTlCIugyuPFus262QoMmY93Jim37JIv70/2fGQ9XyPj1eZ4ukc07kNElMvoi9yKXI2G8071HblfVP/nMY6NJvub5v06ml8iqQyx5j0xfJ5OmxM/skEllPDuScWv/dsiqWfUdyLY5CHBvtHUT0/R55nYPYY+Mm2ivD7m8eHJEVlXFYCcyavdgd8isPcmqC5lUJ7vsk2Uj2n3Iqt1Q3iHz9nzZHmS0KLvaJoPFsWE9yHyRG5loJUpzr2ZxuCYqYnmXjNpZXhQSzCe8q3Lqe74T+uL7GGOVGZl0qoBanehDqrsR6awx+lqM0ZSvDiIeOgKX88xq8WK2TT/eI4tFLigetbI6V2psz02WtD4R6RYZQL32+tXqbHkOp5UKKLd8hwz0+l0D2Xz19vPt7e333369tdevHz/+Kj+8T87g8e30+vnZ3jX6In8esljWSDH5d3vntuQ4CoNhN8dusB2Maw+1F/v+j7k2YCwRHGeBJFNTzs1UTbn5iAMChPRLBMWeV5LZpBOJ54FLzUMllL1VOwtMZv2ysPOpjDzwG0jSjKaRsrgWuTh9Noo1FQeR17RKu0onalJkw7zuIiIHgZLJe8XWVoeQNADJi33fJCJF6dtOBLUV9dstQN7WCEgOAiVOW6F4hGHytvcOyVOxVUyewtmA1XxnTAZHRIYyHhB5DbbxK5XlhrQhz0iV+YiMnXJNyEQmtRPyZKz534Q8ppd0WfJwcrNUQg4nWDKKUR2Tk2DTJmR3KibhLuyQ7PUMlFl2wr1qRF6n50Bny0SamwDJLt1dLCaWVugyY7JLYPRxDJPcVH/uyWv/+vWOzqVFqBZkBhJQ9VZ15o7Mok6hk2nhrcgcHF/sIVmDIflXY3KigJOQOTj+/d3od+ZwtJ2SVUYBp3Rs307JXdK/P5rN51MyxU81IRtgnQ5/Z6ju1LV62yDI1WubZsng1K4ajTC3Cpm4eFCSJ+8F4Vz//mlCHuMQ81rY+VWyjx6qxcrqmn2YQT5QvxuizjGSJ6u4J1mGpC0k+4XJQqeBc8XM3oxurQK79eXHg+m2f4vId8Io62leUiO45LseoBAu1nhNN2dh7zlSKcgqJ9uX6vXC2phx4ys47y1Y9UFq3bjt9JV7V7oqt7/4RLf19kXkP3/Sz1f6H2/zk3x9zE9S9MxF/jw51c8jIleBgr2CLBF7tZ+ZqLNb0sEx3nHVkLFKiMxW0eHoIk+YuPOtIJvEUQJVafZWZxS84xIUpK0ki3ty5jfMPDV2nyJ3F/kiX+RfkJxap/eRUTHaQ3Jq3a/fuQ15eIpMXkBmT5GrlQj5U+T+Y2R+kS9yO/L4NnJqkUV3tt8W+1PlZIq/DcmT9f2KVk1OUpsUzDfaW02uL4f9r8rJqYbBkL0R0hLXqpy5fe0p9t5P8vMxP8n35Se5yP/nQz5Fnrb6Mg9btYa1/848L0iLW/VFXhqTR4miGtlklkXDpPbJpBGSZM9urIi6jMux6unmaA+9gT79+GrU5DVmpa/lXUPenUTciBkmikKy2roHbgKGCrKIfq3JO/KNi2tMVsD9TmegWizv2Yc/0hqtSxNfIwkMDSp9g0jTsE+x7quvNTVmwUjd2EYCWqJXuXE7Y4FiontbPbZxAAkZ8jPmhgJcCOpeIXlAkfJHc5WgSPk289nK+QnLyGA91UZkIcUT5OmBCSsl+6pYh/XMQqtCjs3J3BkIcdIqd/1jqiVZOwPGT8luajX9zs50jv0Jma5PKd6e7C0/OW7VPdWLxmSyzGk3WcVjclCMGdqR2WK6/St9RF6rbLuXoluRqZw6GqRhpwdk23FvTO6kIctn1W0Tz9cZdMwQ6FUwdlSTNmS3D4jl92jvlK7tcj62eFbJWzB2vbxNTXQfJyBUgWutaNCq2W+nXJVeGbVjbM1ate/D2JzqzGy7XvCULyYLnipdn28ohJKwScy+/pTFqyRMfzGcgjdTseuV5/es/d1TQ4zIKD5X6WfI6kH/ismkf3C+gXUTmpOfPK0p9uZT7Mf8JP9+P/H56X6nz3+tOfN3mkfTrAAAAABJRU5ErkJggg==" class="internal" /></td><td></td></tr></tbody></table>

### All

The all value requires markup around every piece of horizontal text, but it is currently supported by more browsers than the digits value.

#### HTML

    <p lang="zh-Hant">民國<span class="num">105</span
    >年<span class="num">4</span
    >月<span class="num">29</span>日</p>

#### CSS

    html { writing-mode: vertical-rl; font: 24px serif }
    .num { text-combine-upright: all }

#### Results

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-writing-modes-4/#propdef-text-combine-upright">CSS Writing Modes Level 4<br />
<span class="small">The definition of 'text-combine-upright' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Add <code>digits</code> value</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-writing-modes-3/#propdef-text-combine-upright">CSS Writing Modes Module Level 3<br />
<span class="small">The definition of 'text-combine-upright' in that specification.</span></a></td><td><span class="spec-pr">Proposed Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`text-combine-upright`

48

9

This property was initially named `-webkit-text-combine` according to a [2011 version of the CSS3 Writing Modes specification](http://www.w3.org/TR/2011/WD-css3-writing-modes-20110531/#text-combine), supporting the values `none` and `horizontal` without `digits`.

15-79

12-79

81

Before version 81, Firefox implemented the property as animatable. This was corrected to spec in 81.

48

Before version 48, Firefox did not implement layout support for tate-chū-yoko.

41

11

35

15

This property was initially named `-webkit-text-combine` according to a [2011 version of the CSS3 Writing Modes specification](http://www.w3.org/TR/2011/WD-css3-writing-modes-20110531/#text-combine), supporting the values `none` and `horizontal` without `digits`.

5.1

This property was initially named `-webkit-text-combine` according to a [2011 version of the CSS3 Writing Modes specification](http://www.w3.org/TR/2011/WD-css3-writing-modes-20110531/#text-combine), supporting the values `none` and `horizontal` without `digits`.

48

≤37

This property was initially named `-webkit-text-combine` according to a [2011 version of the CSS3 Writing Modes specification](http://www.w3.org/TR/2011/WD-css3-writing-modes-20110531/#text-combine), supporting the values `none` and `horizontal` without `digits`.

48

18

This property was initially named `-webkit-text-combine` according to a [2011 version of the CSS3 Writing Modes specification](http://www.w3.org/TR/2011/WD-css3-writing-modes-20110531/#text-combine), supporting the values `none` and `horizontal` without `digits`.

81

Before version 81, Firefox implemented the property as animatable. This was corrected to spec in 81.

48

Before version 48, Firefox did not implement layout support for tate-chū-yoko.

41

35

14

This property was initially named `-webkit-text-combine` according to a [2011 version of the CSS3 Writing Modes specification](http://www.w3.org/TR/2011/WD-css3-writing-modes-20110531/#text-combine), supporting the values `none` and `horizontal` without `digits`.

5

This property was initially named `-webkit-text-combine` according to a [2011 version of the CSS3 Writing Modes specification](http://www.w3.org/TR/2011/WD-css3-writing-modes-20110531/#text-combine), supporting the values `none` and `horizontal` without `digits`.

5.0

1.0

This property was initially named `-webkit-text-combine` according to a [2011 version of the CSS3 Writing Modes specification](http://www.w3.org/TR/2011/WD-css3-writing-modes-20110531/#text-combine), supporting the values `none` and `horizontal` without `digits`.

`digits`

No

15-79

12-79

No

11

No

No

No

No

No

No

No

No

## See also

- [`writing-mode`](writing-mode), [`text-orientation`](text-orientation)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-combine-upright" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-combine-upright</a>
