# ruby-position

The `ruby-position` CSS property defines the position of a ruby element relatives to its base element. It can be positioned over the element (`over`), under it (`under`), or between the characters on their right side (`inter-character`).

## Syntax

    /* Keyword values */
    ruby-position: over;
    ruby-position: under;
    ruby-position: inter-character;
    ruby-position: alternate;

    /* Global values */
    ruby-position: inherit;
    ruby-position: initial;
    ruby-position: unset;

### Values

`over`  
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAJoAAAA+CAMAAADkrPLdAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAKjUExURf////b29v//8fL///38/P39/fn5+QAAAP7+/vv8+6BPAAAAUOXm5ZGRkV0AAMzy/y8AAPTTlP//+//4y4/N8gA+mvv//09PTwAAL0yQzvLz8/f//+7//wAAXuf//3Bvb9SaVgAAQsfz/0IAAFAAAP/90wBNmv/93YGBhMnIyLe4uP7qvPDu7MjLztLT00uY0///58/5/5lPAHh6ef//7drW1Nn5/7Gwsf//98PCwkFBQQAAdwAqjrbY8Z6foPbWn4mJiABcp5/S8vPPjMmRSVxeXtihVptBAJbT96qrrAA+k//31HEAAFqf14nG8P/vwz2LzOrr7OvBgduqbv/yzMG6uL19Ii4uLqlhAABNona452cAAOL7/vrcpv7ksW2x45WXmGOo3e/Ii8CCOu/6/3ltWM/c6tadR4S/5z2FwGx0fpGSps/MzMSfeKHZ+JaNir3s/9ilYUFKTaTL4/z39Nnu+/LOlWZjYQBUh6zh+pI+AIEuAP/36fDz+ruHTN7m8Cl0t/j3+wAAaEIyLW16lpbN8+K4ffjy7qCXlwArggBttYZEAHwAAKmloMHKzI9eMZF9ds6SOAAzRai309zi4ZClst/Kt6dPANCzg8KvmS4uALa2tJaakXOewi1BU66rpej/9KKqu3Kp1J+lrau3vmFrcPTjz9/i0wAuJN7Ho96sYNH38aaHe4eJkerQq3lzc8DR3T9oq2NKLMuUYrBwJcy9ok9cW4mTk9q9tIOixlZ/l8nn+k9GQOvSvC4uQieDxQAtXSpspXKVnaWhlYRzb4iz1FNPWJ+dfk9GH0suAJAAALnC2gB8xWtmTgBAdjZUek19rU5ll+Xl7npOWpZ5U8zq205wf3U/Ky1BLZ1mRSpvkkEtUHEuAAAAlC8AL6u+ngAsaJklsiUAAAmISURBVGje7Zn3VxRZFscLGr0gik0DbUNDI0lAGiUHkSSgIwgoyYAIklYJg4QFUdARWQUcxTGNOYzZ1dExjc6YszthJ6eNf8reF6q6qmka2j16+IF7DlDdVa/qU/fd+733PQQvL7sxaoKd3cQxagL55TQmDdGcHMamCUg2YWyaMNFhguPYNMHp3aG1vQma8PZNE3tRPdu2IRbRDtR/afOzD3xVbX9o/0pLp4L+ma4qg/U/wV/+bzT7DZBnK5n9Bp2/W8Bcb0vnwgLWCsI2ePLrGvm3MZeT3wBtErjbjDbJ2d/NZYZqyAmtIGTAYiT5fZ7yxJ8AjmnpUZv+LaMlxVlCmw/cdIcfKwm6NgE8NlDIdO+3iRa0aIaqyAJa855ptwGOZ2W9Ag9zgG0AuWRoqeXHDYPGAlbzg1mWhc8SraFWOcYt0MPbktccqefw0UEu2eZojpWfkeszYYYNXnOeSg/KoFURuH8Dk32tHJMfkK5iaDfMYkpIWOa3jrA/1Fr0dyXA+4KtaEWl8FBxovHzKaKlmaVXBngKFC2o1DnSPEGTUFPyAy3LWqoaR9qKFlYK2YbhYst8UAmsIGjewib4QOkdTQmgdgjtFgnsGwEsJ8FwaD6RQhcO6o8bZRI4rlJDJ87ZcodN4OyvPFcIPlOpW3OHDOu65QLwnco2Xdv/E4bTdytHm58RO2BAj16DVwDKUNPcAFgjtFWjW83S8MDTGnyGc6tNkhuzgMT535NHrRwRG6hnigIBfJSjgncAfCIIBbB1iDdL8BmPnqtsrKGFfnWnNtuiaqnUV8Eb/e5Wm1X1TCDVqUxNCZVjes9str28225b6G8Hpd4bkdO+GyPRqMLnWOhG7lxbYiMaxnT5sAPOhe+bPMT2Nfx5yIXBgzCgpZqbr/bj1VJjSl4nvOJD+Je3bWgYzivI309PJzY0hFNrSDzCHm6/ACyaBw2awuNno4n5Xs8VIqLElJgPYna2w5xpzF5j6KELcgWb0Wih+kjx8NVW0Vg7ZBqxmEgt0MKFNTJppSjMkvn5Y+9hnhojogW5wHtMkXRLMX51S5cuPQzsK5wTWVPhoZL3Pjh5Yc+u7Ab49mhTCEnUZjZoujRWKGo6fWQR6PbHxz/dqw1eBPCLr2jffG+wjla0e0pKymU1fJHSt/suCe78QKpHOS70j6ax7vMKXqoqfoVHUuE62lTzXHovjIb7pxJDww8CrN8VfkgNPbtCQ4sX8nDMhGyV2HjIzc/fOlqG+Ry5suKbChQtZpjpJLZcxSsm8dFHFi5YzCIiilcydNqjCunVAsAn0jpaaktddHSNGnxCor+hHUsh0HrKCbFO/HFkJrP4QfjvwpnF7MMhAF69XWkANYPu32po2UqC4QKQAxEN/c+itgrk9aEZhjRU1mKNuCkK5hroA+lLIdrsmOJEtOKvMNaWa++f2UU/aJaJ1Xs+9BuYNpTB92z1UwC9OJlt3VydWQ9UAPCB7JnT5YFrNUPF9yng3qhkyUTQ+JzrIvFuTryD0/31Y+61mCip88jkEJqboFsn3TwTekjTsCoA4MnCeGInKr4cNZrJa1hgWOtWBUlxHC2iGIM6NDHeQO52f2Yo/XByEiNyDJPkGmOJhR+W1gFJavHbdD19BDxxEaNwhaCpGgkt4vKVlJSUl5ihO1OaeuPaUTpW2w8eP3sd6A3JjR/aN8yKjY2dVUtf9Fx4LP2QsIArGwZZp6BxYg7P412RrBupBC7nAV8HuRxH7X0RSGIO5XKEWMsPME8rTy16ihgVYc2BE8kWJ9T/3Im9hD1io+iHmA0sSvX4Fa4KtojNOF58b84c9Vqj3jRH7mQ6hqxqlGhupbfP+vpiH7XH17cDX4e2CxfT0q7Wm2pkTt9CtJ31J9FRqov17IPYc7ryN/rl9W+kTyu829jzkhyEqY/RnmSVsrDx+aZoi0dTDRImsZgO3p0sKOWe2Hb+uk73U06LwE7dJqek7zu/gz492xDxIRNIAymj7qwZV8Ox4sTfZWhu3GueI6Hl9J0yoCrS6zSbLjyYw+2wX6e4qpMm+4JaOuR62Q4ko/HVotWEpZ2dzCM9Bp3dMn4prXEaY7ednd2WMOI1bEZHRMvAgmHPvYaIsjqyTnpJC8bqdM4ilFdP4oJ5lzCBUOx8fl5AGDH4y2mfjspLUp5KxSVptDt54dUjoaGYT8Vbr508+Xwt/l0fTsQhNLyRiwhFyxPoXitZ2jrQo+lMWlh5omju+OP8nwAMICzCSSgt9ALsuX8zoblKaHm8vFlHS8Uun+ekn6Sj5GsZ2vMltH/cBEm1k/kRzXwUtT8GORp5GHN1Ab1ZLivo/bcUaK10eGw1OZ43ElohJrEMzVPmTGsTyqP6Dh3C9kym84pOUgN6Ilmzl5cqRzNV9Ezp/sOjkUE0XZzajLK0UaDpWKOqFg+mvZYSjmYQQ0N5Zo/GKTUFkqscjd7T8caeszXA0sQaGr6irlPM0OHQ3hPfYrleLOmilNMhDA3T83Ex6W5RfP3O1BuGQ+P7XOUjdbnBG0E99+THEtpa4xJixm1ytDVtXmgTM6F/pRc/EneBaHJTNFYXylnFauHliaJFmqHlN4VEh7Se26u1jraKSNUXOziaXDysx5rPzz+26hnagJcxCssaSkNrCSnwqGlJWDn6DSJastG4jLhZmglH1uMkxVlFuwQ+L5kCsOfI7H1raEnnXWjMi0NWoFCl6ytJijYTcagUa72rKW9cFaE/dA2jREM/eeix/aR7O1iTlniJZvxB2pKCNRqiZrgwzzbw/ydtr8YinStD+6QEfPxJR1vuFgCfoRiXstZFiSbvuavAfGtQiUZXhvY3yY7H3s1bFBc6GOlK27Hox3/ME9Nghl6mh7RIkvD0MhpjccXS87RmK65bBvHn2SupnCBastGriqHpTFr2aYC4uBgGrYp0W4LmIC+OD1qysjo6OrJe3NuqFqPNUaYzut6UeLJK2NlHNn06RfEQcgItTfpqhkY2bsKe9cbRJdKerLroq74d9w5byFEFWpm4Luo6dH3ordP1Q3bX5TZATifcJGi042ip23/tInZnD26HnN61GdfydB8xgy7q6BNzNirGr7e6Dk04aPpfxvbzoUd2Hk0LYZY2paLCfFMr5lbT1Y5pL7LQ6kLqr/Hcd9KS/eh93VreJs6WXuRbkoHBJ05Ju3YJscV9aSFpaWlXKlLO1I6ka9u18q1r5c7jBEvbkda3UzV3akVXd1nasdK8g02s4bdS33zou/rP3jjaONo42jjaONr/AGBZNol7w3N6AAAAAElFTkSuQmCC" alt="Over example" width="154" height="62" />Is a keyword indicating that the ruby has to be placed over the main text for horizontal scripts and right to it for vertical scripts.

`under`  
<img src="data:image/png;base64,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" alt="Under example" width="156" height="68" />Is a keyword indicating that the ruby has to be placed under the main text for horizontal scripts and left to it for vertical scripts.

`inter-character`  
Is a keyword indicating that the ruby has to be placed between the different characters.

`alternate`  
Is a keyword indicating that the ruby alternates between over and under, when there are multiple levels of annotaion.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>alternate</code></td></tr><tr class="even"><td>Applies to</td><td>ruby annotations containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ alternate || [ over | under ] ] | inter-character

## Examples

### Ruby positioned over the text

#### HTML

    <ruby>
      <rb>超電磁砲</rb>
      <rp>（</rp><rt>レールガン</rt><rp>）</rp>
    </ruby>

#### CSS

    ruby {
        ruby-position:over;
    }

#### Result

### Ruby positioned under the text

#### HTML

    <ruby>
      <rb>超電磁砲</rb>
      <rp>（</rp><rt>レールガン</rt><rp>）</rp>
    </ruby>

#### CSS

    ruby {
        ruby-position:under;
    }

#### Result

### Ruby alternate

#### HTML

    <ruby>
      <rb>A<rb>B<rb>C</rb>
      <rtc>Above</rtc>
      <rtc>Below</rtc>
    </ruby>

#### CSS

    ruby {
        ruby-position: alternate; /* this is also the initial value */
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-ruby/#rubypos">CSS Ruby Layout Module Level 1<br />
<span class="small">The definition of 'ruby-position' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`ruby-position`

84

1

Implemented as a non-standard, prefixed, version of `ruby-position`, `-webkit-ruby-position`: it has two properties: `before` and `after` (both equivalent, for ltr and rtl scripts to the standard `over` value used with `ruby-align: start`).

84

79

Implemented as a non-standard, prefixed, version of `ruby-position`, `-webkit-ruby-position`: it has two properties: `before` and `after` (both equivalent, for ltr and rtl scripts to the standard `over` value used with `ruby-align: start`).

12-79

38

No

Internet Explorer 9 and later support an old draft values: `inline` (equivalent of having `display: inline` on the ruby), and `above` (synonym of the modern `over`).

70

15

Implemented as a non-standard, prefixed, version of `ruby-position`, `-webkit-ruby-position`: it has two properties: `before` and `after` (both equivalent, for ltr and rtl scripts to the standard `over` value used with `ruby-align: start`).

6.1

Implemented as a non-standard, prefixed, version of `ruby-position`, `-webkit-ruby-position`: it has two properties: `before` and `after` (both equivalent, for ltr and rtl scripts to the standard `over` value used with `ruby-align: start`).

84

1

Implemented as a non-standard, prefixed, version of `ruby-position`, `-webkit-ruby-position`: it has two properties: `before` and `after` (both equivalent, for ltr and rtl scripts to the standard `over` value used with `ruby-align: start`).

84

18

Implemented as a non-standard, prefixed, version of `ruby-position`, `-webkit-ruby-position`: it has two properties: `before` and `after` (both equivalent, for ltr and rtl scripts to the standard `over` value used with `ruby-align: start`).

38

60

14

Implemented as a non-standard, prefixed, version of `ruby-position`, `-webkit-ruby-position`: it has two properties: `before` and `after` (both equivalent, for ltr and rtl scripts to the standard `over` value used with `ruby-align: start`).

6.1

Implemented as a non-standard, prefixed, version of `ruby-position`, `-webkit-ruby-position`: it has two properties: `before` and `after` (both equivalent, for ltr and rtl scripts to the standard `over` value used with `ruby-align: start`).

No

`alternate`

No

No

88

No

No

No

No

No

88

No

No

No

`inter-character`

No

No

No

See [bug 1055672](https://bugzil.la/1055672)

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

- HTML Ruby elements: [`<ruby>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ruby), [`<rt>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rt), [`<rp>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rp), and [`<rtc>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rtc).
- CSS Ruby properties: [`ruby-align`](ruby-align), <span class="page-not-created">`ruby-merge`</span>.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/ruby-position" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/ruby-position</a>
