&lt;input type="time"&gt;
=========================

[`<input>`](../input) elements of type `time` create input fields designed to let the user easily enter a time (hours and minutes, and optionally seconds).

The control's user interface will vary from browser to browser. Support is good in modern browsers, with Safari being the sole major browser not yet implementing it; in Safari, and any other browsers that don't support `<time>`, it degrades gracefully to `<input type="text">`.

Appearance
----------

### Chrome and Opera

In Chrome/Opera the `time` control is simple, with slots to enter hours and minutes in 12 or 24-hour format depending on operating system locale, and up and down arrows to increment and decrement the currently selected component. In some versions, an "X" button is provided to clear the control's value.

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAANMAAABECAMAAAAsuvAQAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAC9UExURbPU/9jY2IKCguzs7AAAAFFRUS8vL/Dw8f///06P/vf392dnZ0ZGRgsMDf7+/qzM9aOjox0fIq/Q+uDg4Hl5eSoyPJi02CAmLigoKImjxPz8/MXFxUpYatTU1GR3j6+vr3iOqz09PUNPX5264Ji+/leV/o6pyzE6R8zMzKfF7lZWVjc3N4ObuxYYGjZATo+PjyUsNaLA5zxHVfX19dro/1lqf19fX729vYyMjFNidpOv0pqamubm5nCEn0xMTI80vtEAAAM1SURBVGje7dprW6pAEABglFnEclFuXlNDvECKpuYt6/z/n3WWJRALhdNzqKCdL0m6wuvMzgIPnJi/4JiJmZiJmZgpV6bhqJzdGA2jTMNytmMYYRqVnzJccE/lUYSpXM70LDodPjN9Y5Suxi80cTHBTMzETMz0400I5c6E0DtU9k0IvUdl3oTQB1TWTQh9RCUwKfcTjCevVYpQWncy4PmrfcXU3k2hGP5HH4NQuHB4RXBDfqit3a0aQJ9+hQaQxIRQBCretFzRvcJq6SJa3gbo9UsmyULk/bBJNSDORMJwP7EAuHVx6jSRCaEoVKypegeTMafMGnDnZmq8eVa8LSXapG4x1s7ydKMBal4xuYhSXwDEk62m0ezSzD5AeuvTDD/SlMwcPDvNo3vQzUgTKZo/Fl8Jm8jxdYQYkyh2m27VFYU9LERxvUWL9EzKAXpUUR3ARglMrbBJfZBrbX+gtViLZybVkK1CvGl9S8ZIRWFnkHxZzr6Wnmmp45aXGRlWdihPg6pvksiUoAUTRNhEKm8hJTCRF0UCE7oa3rW1ZjdFU71BS88cuH3BDNLUaIy5ZKY+3pbEZHlauKaC5WiqcXuToqkFE5t0cxkee40GnVi9yYSkzAz18rPae2dS6ZxPYNrJskVNpe30SKZWJ10TSRI+2PU308ZtvHhgnvVySYw2kco7SvEmiT82Yd8mA8nnjgCVl3RNeo8kicwp3+T2i+cBeN0wepcnUx/TLFw1eYGLa3eg8eKuTXspTdOzTHZ3oCuToy+DHkFWrYMSb1INgU60WNNU60p0YIUny4FjiWmaTB308Vmr8+IV5na8qQahiGYFfY/+BlNi8iJFE0mItz4p/gvfRIX/2VQQAlNBSO884v5t5rQcZ3wi2QNPGNv3/AOMX5++0LSc++d7veA0otqaw3wZvT7d8DxfqIBG/qxTN33yHJar617p0FNYUopezM0La27nVGy1fzZ1ThvJ8vTJaw3O7umAVzO/35E+qG/G3KU192tNn70mTHSdK7Frd3aP5dfdC8vlPUt2v5yZmOn7TD80mCkbptj4NaY8PkOVx2fd8vhMYm6CmZiJmZiJmZiJmb4m/gLoL8ZqDMJ6NwAAAABJRU5ErkJggg==" alt="12-hour Chrome time input" width="211" height="68" /> 12-hour

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFIAAAAfCAMAAABDNGobAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAFQUExURf////39/ff2983Nzd3d3dPT0+vr7MzMzMjIyAAAAPHx8ezs7OPj4///9/Dw8PT09NfX1//7/1hYWIaGhgAHTNX6//jQkv/20nYLAMvLy9ra2vX9///qvff//+ft9+/p5+Xl5ejo6Pj4+HFxcVJSUsrKyvn5+ZbT94a/5/DGiJIRAAENY83v/0sEAP//7/f3//fz7wCX0t37/9Xt+wBOpf/55wA2jP/63s33/wADMTILUv/wxui6jPjbvazQ7+iye9eaSWGn1oRye3Gv3ufY3r+/vzICAPfv776JMO/w//firdbn99eue4rP9/fj1ub7/+iuYvjWrc7Q57zv/wEXjI4SMfjbznG7765mAL6KSf/z7//uzgIZlP/z551LAM7U59bI1kiLvXGn1i2Dvd+mc6Pb90+j1gERcwB0vaPb/wAxSo1KAAA5pfC6eufOpQBotbLfaLoAAAGaSURBVEjH7ZXXT8NADMa/NIO4TQd0UlbLhrLpZO+99957/v9v5HIBWpTyQoQqwfdgx2fpJ599dwH+VfIqs0cFSHsK+1tIjxbVPD9EOiRRFSWHGcXjXsEbjxdBHijMuuvmCwh1tfkOcKlcLl5jTNCtEPNYIveJ0qs47CRq/cx0nRBdAuHIA93wGtV3GXVqTtQ31MOpWSHd25vu9mWkNhA6qvnIuM9qwrksQk8YDATZgqSqTkmVnKoqsdAnwN/oh+CzrNKBrvYW9tGWZMjhiRGerB4IIpTE4ICBFBlLYWSRhTIqK7wVlbq3Hs/aVpVe1x7tsmCMeo3FK7oDUpGcGbItK1CY40iuIsilQIfh1xN9zE1V8WQ4co9Quv/lts+yyu+Qc4mOnX6sLGLB6NoQTer2+BSZyDWeXxEOZC16+S2yeoaIWtBG5sRHaZyt6gfgHMg8El1YTZz3UizaS0Pls+aGy7nr6c53X8+lbE5ctu/2SAqaG5qhSPbdcZfPuD0+l43PRlRWBEWO2vkSCVrTdJMm/Mp7af+/518lqjehFSqERhMYtAAAAABJRU5ErkJggg==" alt="24-hour Chrome time input" width="82" height="31" /> 24-hour

### Firefox

Firefox's `time` control is very similar to Chrome's, except that it doesn't have the up and down arrows. It also uses a 12- or 24-hour format for inputting times, based on system locale. An "X" button is provided to clear the control's value.

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAGoAAAAdCAMAAAB12AncAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAFQUExURczMzNHR0f/+1//2z5ubm7Ozs873/////4WFhQAAAPf//9b+/ymY1/f399ieRkgKRwAGSe/t5///9//+32AHAHAKAM6PLo0yAP/+5/jUl8nJyf/z622o1wEQb/f3////7/f37wCc0+y7d//uv1yo10gHLwCQz/fv9wBPp7LQ6+fv90wEAOvqv6VOT6Xf+wADLzAKT//yx5HP74uPk//uz3gMAABjt//399iXLkOg1/jfv+i/j22w3+fY34hwd+i3h9imXtb3/zAJR8/X56BJAJ7A59fI10SQv6B4dyqIv+Cnb//21494d8iHRt7+/0uo1zAFL8CebwByv5BIAAA1j9bv9+fOpwA4pwAvR7hwLi5PX63m777n9wEMX19gb26XpwBip5hhX77Y9+jHp/fu1563z6B3R3d4h972505uX6iOX1A3l0uw309Np09Kh12PrwXnu1EAAAGESURBVEjH7ZZnU8JAEIYJIdnbIEgvKhaUJigde++99967/v9vXgggwTEGB/Mp72SyubLz5Hb3LjGAZjLoqEagDP8rGUqLyOkotWJMhJiYX1GR4n1A+OZv7602CrJQkCiTRRE1gbYpAKcXh2r8O2YRlwCM+UPckA34FrMkG4Obh2vIrc6JPSUSZSmiWhPTPIDD7mmqQTnmBTbJg/8A0jaz7B228OIeMzlXATyYoR0thDAcIRxDrWIAjc28aKxl1PB4rDzUnTKDPwrplAxFPczgCfvytkfvmVlaFAccvb6WpQ5lxa7S0zJu03C5k5WOskfo9Nb7yr4/P31cib5i6DgQSYTUhYKxSoGsuPvBv7u3H1iXo+LH53cC+5bAk766UGyoiBoMl9ojOColcQacFBUsAGvjZSh2U2yzL0LEUUSpDeAkIraB0YUYkDISxB4pUXHEBVqbO+K4bFF0Lp1yhJewhlGhjrL4WZ3t1UZBKou9EVK5hTU9mPST/W8o7T74+s+ZjpLpE1BTaBJuXJF7AAAAAElFTkSuQmCC" alt="12-hour Firefox time input" width="106" height="29" /> 12-hour

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAAdCAMAAAAKCRstAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAJcEhZcwAAEnQAABJ0Ad5mH3gAAAByUExURf//////0+fn5wAtg4eHh9P//9ODLXp6en9/fwAAAIMtAP+rWbi4uP/Tgy2D0/X19aCgoFmD0wBZq1mr/9PT05OTk6v//wAAWf//q8fHx6ioqL+/v6tZANODWYPT/9/f34NZg1lZq1ktg7CwsC0tg4OD04RYnOIAAAECSURBVEjH7ZXdkoIwDIVDDTWVv4rgCqi4q/v+r7hpoQy6HbnpzQ57bjpzmH6TkwQA+FcIbYPJAYNVtgpg0aRtV4UD9khGuvACpcrtmSi1iX/ddS6fpfMqGlX7gEmZ7S2X7yX5K8+52SMGeRjzItUpETZEqTfyALTwERjtPo6zItm9XAFOn1OBGlIUAgnfAaPdFHkGHF0L/Boe3037oBCmkQsVytw3Apk/AzkuoYCOloHRLfYAjWv65yJ3hidaC34DPPMVWb5Gdu7pG6ahCB4G59U8HO0BSqXsZnCzPD2c3PNsbVou0a4N9mEWu6iHNcQq2KvXMBK1WNPX5q8CQ/+kVqYfFT0RXImgoE8AAAAASUVORK5CYII=" alt="24-hour Firefox time input" width="80" height="29" /> 24-hour

### Edge

The Edge `time` control is somewhat more elaborate, opening up an hour and minute picker with sliding reels. It, like Chrome, uses a 12- or 24-hour format for inputting times, based on system locale:

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAQYAAAGVCAMAAAArGa/jAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAACcUExURfLy8mFhYTMzMyEhIcLCwu/v7/X5+pHB5////+bm5t/g39HR0XSaucDAwNnZ2Xx8fGRkZKmpqYqKij1+mnV1dUtLSwMDBJ2dnenp6bOzs2lpaZOTk6+vr4+Pj2xsbF9+lxQaIPLt3dvt8rFqHCg2QICqzE5nfOvy9G+SsD4+PhxqsczMzDxPXxxeqkme19eeSapeHLTh8rF+fvLhtN2/g0oAAAtZSURBVHja7d0Le6K4HgbwBGVVKBBYBETUdqZ22tU5e87Z7//dNhdA6lyMElTkzTOjeAvkR/IHSghkisQTAQEYwAAGMIABDGAAAxjA0JJh1GXqEUOHMwEDGMAABjCAAQz6DKFlWQF/ZlYQWMzyjr7l//CORvIsa/6LD5qvlpbF9BmOdnVWow81QUd+/WbMv/Mhnni5Gm+fZlha/NtzvjT8ef6TEl/EYC2nS3aSQbxg4Tm1IY4PBY5DxbCKmwwrzkKnMQ35k3cGgyqlxdefSCF/6cl1FFi8LJKBT4VyzQX8I38azrmaFS6rFe7L2hQw8VD+RhZWsIrvhHP+tq8+8cUbdVUJJIH8nK8JnuFSTv2GgYpf+KOVqsaSwfuYHjHw9+Mw9lfxGQzl6mFL4TEP+aPPl5+Fy3lZDzjDdDmXAFZYM/C3eTFkmfmP+NsBf13/RjF4AW9rVhhyxLnF2141O/6aBfKXkjbkQAGbzudyar78JYM3GtHpDwwf3jEDjafUoys/DvUZwnLFBDWDrM2+qKyiGLJgfOHF9JJVDMupwGo0HJ8XZFr/RpR0qarZPBTl58VWP+A5iTkqfF5yySRf8zxF7ur3v6oNK9r4VDKIch/FBt5wqC+rRJvaoBr13CojZ8nAjhgOVVuEWMVQ/0Z8uBT1SjSzY4blgUGyic/5h1oM/uiYQR0kxs3aIKqIf5g+LzYcMdSh61Nt8A8M06pR8M8btaFRQ4Ttb2uD+FwxnFUbPjeK6fS4UVzEcNhSlAwyfgdinc2XBwYZG5biBZMM3rxkEG8FiqHxG1+UnE+HP9YGGRtY2SD5r0XsELHhFINXrXXFsBK1gP6CQb6zWl2y31AxiDfUliJo1Aa1pZCPqjYE1TZfbEjmoWCof1NmwR8DtbZrhqllNXYqxMaBf4tZyu90bXjgvcjQws40GHBoBYZLGcYDSz9nGI2JyTQ+lV3siUfqOWxHiJ1GJ/ObmU0/Z5hOb8RAVnGW7djgGcgqz1fhUBmikD841C1fFQNlKCKbEC/gcYG/8JkzUAYn97KM8W8VGX9ekIEycIc8F19Ky2czDEVQ9Ivh3Pz0FArxb+gMkkDP4YEZSgAth4duFP0LkWAAAxjAAIY7zY+AAQxgAAMYwAAGMIABDL1myOSjnWWZPVgGO/OpODthe3nOdvZQGXYslwwec8hYnM8dJkOwcCVDLM7bRelwY4NkcKRFEQ+cwaVi0qNgAAMYPsWGcOixQXZ7saPF0BkWLMu8fMA7024u+7gs8jwnA2bAoRUYwAAGMIABDGAAAxjAAAYwgAEMYAADGMAAhqssdlY+21mvGAp57WxBKY3aL3bVv4FPnLwm954YUlV6RzzE7U/EV/0b7DRnPWJwqXO4rt7AOceqf4ObO2nUq0ZhlKE6a/Up354xaIy3MACGgjpgIDE1stj9ZnBoSsAgR+AAgxcTMKidSJ48Awx5xbDCoRUOrcAABjCAAQxgAAMYwAAGMIABDGAAAxjAAAYwdLzYarQCm6feMTgnz9tpLrZtq/4NPuPJ7xeDS6kphh1jMquVI/7o369hLOLCNcUQNLM6eSbs3hqFMYZPWYFBNRAHDLbPCjJ4BrtgHhk8gx2xHu4+GWfQOKs/BAa6szX2Ix+ZQWwfHCZT1DMGHFqBAQxgAAMYwAAGMIABDGAAAxjAAAYwgAEMYOgZgz2z5SNPPWOIKKWFGQZ7pv7IvVuv1/GsdX6RulLYrYeWSH//J/Q2DF4h+nmYuRx1l6vxG8Td1Vdx2/wcGnmKoSy9Q7tjUMyREYZq/AZJQtvmV6ReVNYGVVuLqB8MzTM/i9ajjseuQ12Zpxrbn1CvY4a4MMvAI+R60TI/UXZ5xxM+IVuHFzndMkSmr9EO1mu/bYhM03KEEc4gW0fkdsrgUK0T0Gc2ioC1PJUrG4SI3aJaxC5xY9Ilg6e1mTibQd6doUV+5eXzkWIoUpJ6XTJons4+i0EMfZXF41b5qXAl8pMBkjox6ZIhTYlxhpSHyHTdKr9q7XANyVBERacMkap8jiGGtaMi5Dpol18VtQuqGBz10O0GE4dWYAADGMAABjCAAQySYWIyPT1N7jq/CRjAAAYwgAEMYAADGMDQa4ZtPbHtF8NzkiTvhhi2T0lV+uS1ZX5iuZKNnCjzfE/eOmN453PaaDmcZnjnC14u8lt7Br5gW1Hw56r0rx0y1LM0wDB6ey8Z3pO9CYbJ2zOfeH1WVS157Zgh2RiKDRXD85MZho1g2Ki1tN93zLB/nphl2O8nhmrDq5jYyLySbZcMb8mJJnc+w340McMggxafELlu9pOOa8Ob2UaxSbbb7f5125IhKQMuZ3jb86f3rhlk3TPHMEqek+fDRqNNoygntsnknS9ivxhUvDESG6qJ/eb1vVOGvVz4zZ0zbOVGs0OGt8TgXuTkqSOGyetm0n2jwKEVGMAABjCAAQxgAAO6eYABDGAAAxjAAAYwgAEM/WJQ1+LOdAZwuDuGVOtaTP3xGxy65qlvDA41xFCN3+DSPjaK2FRtqMZvcOMeMhSpa4ihupjWi/s3totLiWmGBY8MrF8hUoyYYZpBhV2/TwxqhATzDKdHCLknhnKYBJ0hj85kiIpexQZivjbI8RvoeOgMEd9QRAEZMIMcvyHlW4oVDq1waAUGMNwjw6xOQ2OYNRIYwAAGMIABDGAAAxjAAAYwgAEMYDDJYNfpBgyZerKzLLv+nZPtRjqXQQ4tbObGDHbmq79xZ+F6vR7fmiGT/zQZYs9YbdixvLyr+uomjaIqedasDZkmg2uMoerf4AXkRgxHjSLTbxTUNRgbyrNWBQ8N2c0YZH1QjUL+1zuxrxkazrq5fL5eL+2bNYpLQqRceKO36XBozh9ZeBdbiuyMDWYRm2XwdPLshCGryk4ONUN7Pp5RBsJ2pLzTyA1qw+WNwvQtfFaiPYTB9RmyuiGUDJnuBtPzxIpzjTKMcz/z81vuPsktRaWid7cSvbtTnNO/gYw1diI7iw3ZxY3iQQ6tftyZPm9L8TAMWXP3yT7nmOLRakO1pfijTkNj+KORwAAGMIABDGAAAxjAAAYwgAEMYACDSYZvdRoaw7dGuu1lJeLMpejcoHES886urnHUXbsNMJT9G9xcJBr0isHTvZ+4fv8GSRL363JUar5/g0hhvy5H1Tp9qb3YNYNNx71iSNOUxwbjDGFAesUQib4NaWyY4XRkuDeGiKixLIwy7BghPWsUMk56ZhlUrn0LkaZrg20qvytuMIuyZRhk2FHSNwaiuROpx5BLhkXQP4bHObQCAxjAAAYwgAEMYAADGMAABjCAAQxgAAMYwDAYBtWpwda4RPtxGarxG+wwz5k/WIaqf0PIHLI42W3iYRmq/g1y3PWTw2M8cGw4XJzct94uHTC4zM/CgAydIfPyPL/BSD/3xSBHuHHY0GODqhI3GMbi3hj4vpPtDZ2BBFGW+WwxYAbVvyHgIXJBhsuAQyswgAEMYAADGMAAhg4ZZmYTGMAABjCAYYgMxYd8+ijOZvizTo9QG6SDlsJs/GcjPRiDcNBTeGyGWZEUswsYECJ71r/hQRnq/g2pXv+GB2Wo+jcsA/5tZg+VoezfoK7x1bi5/MPGhuY5zOhuGAaWwPBbBjKoBAYwgAEMYAADGMAwKAb7cERqf7szhpf//+9aDH9//1LN9Ot/7ovh5etfX67F8PK1dLh4pl0xXFOhdrh8ph0xXFehdGgx024Yrq0gHZz/Xj7TThiuryDmmXy/fKYmGf55/3IzhTtiaB2o2lVA5+v3+2gUbQNVy2b4crmD2djQMlC1DUaXOxgOkbyF3k6hhYPpLcVLcX0F8vdfd7szjSNMMIABDGAAAxjAAIYhMqCbx9ATGMAABjCAAQxgAAMYwAAGMIABDGbSvyp2XiL8g8RpAAAAAElFTkSuQmCC" alt="12-hour Edge time input" width="262" height="405" /> 12-hour

<img src="data:image/png;base64,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" alt="24-hour Edge time input" width="174" height="390" /> 24-hour

<table><tbody><tr class="odd"><td><strong><a href="#value">Value</a></strong></td><td>A <a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMString"><code>DOMString</code></a> representing a time, or empty.</td></tr><tr class="even"><td><strong>Events</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event"><code>change</code></a> and <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event"><code>input</code></a></td></tr><tr class="odd"><td><strong>Supported common attributes</strong></td><td><a href="../input#attr-autocomplete"><code>autocomplete</code></a>, <a href="../input#attr-list"><code>list</code></a>, <a href="../input#attr-readonly"><code>readonly</code></a>, and <a href="../input#attr-step"><code>step</code></a></td></tr><tr class="even"><td><strong>IDL attributes</strong></td><td><code>value</code>, <code>valueAsDate</code>, <code>valueAsNumber</code>, and <code>list</code>.</td></tr><tr class="odd"><td><strong>Methods</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select"><code>select()</code></a>, <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepDown"><code>stepDown()</code></a>, and <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepUp"><code>stepUp()</code></a>.</td></tr></tbody></table>

Value
-----

A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) containing the value of the time entered into the input. You can set a default value for the input by including a valid time in the [`value`](../input#attr-value) attribute when creating the `<input>` element, like so:

    <label for="appt-time">Choose an appointment time: </label>
    <input id="appt-time" type="time" name="appt-time" value="13:30">

You can also get and set the date value in JavaScript using the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) `value` property, for example:

    var timeControl = document.querySelector('input[type="time"]');
    timeControl.value = '15:30';

### Time value format

The `value` of the `time` input is always in 24-hour format that includes leading zeros: `hh:mm`, regardless of the input format, which is likely to be selected based on the user's locale (or by the user agent). If the time includes seconds (see [Using the step attribute](#using_the_step_attribute)), the format is always `hh:mm:ss`. You can learn more about the format of the time value used by this input type in [Time strings](../../date_and_time_formats#time_strings) in [Date and time formats used in HTML](../../date_and_time_formats).

In this example, you can see the time input's value by entering a time and seeing how it changes afterward.

First, a look at the HTML. This is simple enough, with the label and input as we've seen before, but with the addition of a [`<p>`](../p) element with a [`<span>`](../span) to display the value of the `time` input:

    <form>
      <label for="startTime">Start time: </label>
      <input type="time" id="startTime">
      <p>
        Value of the <code>time</code> input: <code>
                "<span id="value">n/a</span>"</code>.
      </p>
    </form>

The JavaScript code adds code to the time input to watch for the [`input`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event) event, which is triggered every time the contents of an input element change. When this happens, the contents of the `<span>` are replaced with the new value of the input element.

    var startTime = document.getElementById("startTime");
    var valueSpan = document.getElementById("value");

    startTime.addEventListener("input", function() {
      valueSpan.innerText = startTime.value;
    }, false);

When a form including a `time` input is submitted, the value is encoded before being included in the form's data. The form's data entry for a time input will always be in the form `name=hh%3Amm`, or `name=hh%3Amm%3Ass` if seconds are included (see [Using the step attribute](#using_the_step_attribute)).

Additional attributes
---------------------

In addition to the attributes common to all [`<input>`](../input) elements, `time` inputs offer the following attributes:

<table><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>list</code></td><td>The id of the &lt;datalist&gt; element that contains the optional pre-defined autocomplete options</td></tr><tr class="even"><td><code>max</code></td><td>The latest time to accept, in the syntax described under <a href="#time_value_format">Time value format</a></td></tr><tr class="odd"><td><code>min</code></td><td>The earliest time to accept as a valid input</td></tr><tr class="even"><td><code>readonly</code></td><td>A Boolean attribute which, if present, indicates that the contents of the <code>time</code> input should not be user-editable</td></tr><tr class="odd"><td><code>step</code></td><td>The stepping interval to use both for user interfaces purposes and during constraint validation</td></tr></tbody></table>

### Note

Unlike many data types, time values have a **periodic domain**, meaning that the values reach the highest possible value, then wrap back around to the beginning again. For example, specifying a `min` of `14:00` and a `max` of `2:00` means that the permitted time values start at 2:00 PM, run through midnight to the next day, ending at 2:00 AM. See more in the [making min and max cross midnight](#making_min_and_max_cross_midnight) section of this article.

### `list`

The values of the list attribute is the [`id`](https://developer.mozilla.org/en-US/docs/Web/API/Element/id) of a [`<datalist>`](../datalist) element located in the same document. The [`<datalist>`](../datalist) provides a list of predefined values to suggest to the user for this input. Any values in the list that are not compatible with the [`type`](../input#attr-type) are not included in the suggested options. The values provided are suggestions, not requirements: users can select from this predefined list or provide a different value.

### `max`

A string indicating the latest time to accept, specified in the same [time value format](#time_value_format) as described above. If the specified string isn't a valid time, no maximum value is set.

### `min`

A string specifying the earliest time to accept, given in the [time value format](#time_value_format) described previously. If the value specified isn't a valid time string, no minimum value is set.

### `readonly`

A Boolean attribute which, if present, means this field cannot be edited by the user. Its `value` can, however, still be changed by JavaScript code directly setting the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) `value` property.

**Note:** Because a read-only field cannot have a value, `required` does not have any effect on inputs with the `readonly` attribute also specified.

### `step`

The `step` attribute is a number that specifies the granularity that the value must adhere to, or the special value `any`, which is described below. Only values which are equal to the basis for stepping (`min` if specified, [`value`](../input#attr-value) otherwise, and an appropriate default value if neither of those is provided) are valid.

A string value of `any` means that no stepping is implied, and any value is allowed (barring other constraints, such as `min` and `max`).

**Note:** When the data entered by the user doesn't adhere to the stepping configuration, the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) may round to the nearest valid value, preferring numbers in the positive direction when there are two equally close options.

For `time` inputs, the value of `step` is given in seconds, with a scaling factor of 1000 (since the underlying numeric value is in milliseconds). The default value of `step` is 60, indicating 60 seconds (or 1 minute, or 60,000 milliseconds).

*At this time, it's unclear what a value of `any` means for `step` when used with `time` inputs. This will be updated as soon as that information is determined.*

Using time inputs
-----------------

Although among the date and time input types `time` has the widest browser support, it is not yet approaching universal, so it is likely that you'll need to provide an alternative method for entering the date and time, so that Safari users (and users of other non-supporting browsers) can still easily enter time values.

We'll look at basic and more complex uses of `<input type="time">`, then offer advice on mitigating the browser support issue later on (see [Handling browser support](#handling_browser_support)).

### Basic uses of time

The simplest use of `<input type="time">` involves a basic `<input>` and [`<label>`](../label) element combination, as seen below:

    <form>
      <label for="appt-time">Choose an appointment time: </label>
      <input id="appt-time" type="time" name="appt-time">
    </form>

### Controlling input size

`<input type="time">` doesn't support form sizing attributes such as [`size`](../input#attr-size), since times are always about the same number of characters long. You'll have to resort to [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) for sizing needs.

### Using the step attribute

You can use the [`step`](../input#attr-step) attribute to vary the amount of time jumped whenever the time is incremented or decremented (for example, so the time moves by 10 minutes at a time when clicking the little arrow widgets).

This property has some strange effects across browsers, so is not completely reliable.

It takes an integer value that equates to the number of seconds you want to increment by; the default value is 60 seconds, or one minute. If you specify a value of less than 60 seconds (1 minute), the `time` input will show a seconds input area alongside the hours and minutes:

    <form>
      <label for="appt-time">Choose an appointment time: </label>
      <input id="appt-time" type="time" name="appt-time" step="2">
    </form>

In Chrome and Opera, which are the only browsers to show up/down iteration arrows, clicking the arrows changes the seconds value by two seconds, but doesn't affect the hours or minutes. Minutes (or hours) can only be used for stepping when you specify a number of minutes (or hours) in seconds, such as 120 for 2 minutes, or 7200 for 2 hours).

In Firefox, there are no arrows, so the `step` value isn't used. However, providing it *does* add the seconds input area adjacent to the minutes section.

The steps value seems to have no effect in Edge.

Using `step` seems to cause validation to not work properly (as seen in the next section).

Validation
----------

By default, `<input type="time">` does not apply any validation to entered values, other than the user agent's interface generally not allowing you to enter anything other than a time value. This is helpful (assuming the `time` input is fully supported by the user agent), but you can't entirely rely on the value to be a proper time string, since it might be an empty string (`""`), which is allowed. It's also possible for the value to look roughly like a valid time but not be correct, such as `25:05`.

### Setting maximum and minimum times

You can use the [`min`](../input#attr-min) and [`max`](../input#attr-max) attributes to restrict the valid times that can be chosen by the user. In the following example we are setting a minimum time of `12:00` and a maximum time of `18:00`:

    <form>
      <label for="appt-time">Choose an appointment time (opening hours 12:00 to 18:00): </label>
      <input id="appt-time" type="time" name="appt-time"
             min="12:00" max="18:00">
      <span class="validity"></span>
    </form>

Here's the CSS used in the above example. Here we make use of the [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid) and [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) CSS properties to style the input based on whether or not the current value is valid. We had to put the icons on a [`<span>`](../span) next to the input, not on the input itself, because in Chrome the generated content is placed inside the form control, and can't be styled or shown effectively.

    div {
      margin-bottom: 10px;
      position: relative;
    }

    input[type="number"] {
      width: 100px;
    }

    input + span {
      padding-right: 30px;
    }

    input:invalid+span:after {
      position: absolute;
      content: '✖';
      padding-left: 5px;
    }

    input:valid+span:after {
      position: absolute;
      content: '✓';
      padding-left: 5px;
    }

The result here is that:

-   Only times between 12:00 and 18:00 will be seen as valid; times outside that range will be denoted as invalid.
-   Depending on what browser you're using, you might find that times outside the specified range might not even be selectable in the time picker (e.g. Edge).

#### Making min and max cross midnight

By setting a [`min`](../input#attr-min) attribute greater than the [`max`](../input#attr-max) attribute, the valid time range will wrap around midnight to produce a valid time range which crosses midnight. This functionality is not supported by any other input types. While this feature is [in the HTML spec](https://html.spec.whatwg.org/C/#has-a-reversed-range), it is not yet universally supported. Chrome-based browsers support it starting in version 82 and Firefox added it in version 76. No information is yet available about when or if Safari will add it. Be prepared for this situation to arise:

    const input = document.createElement('input');
    input.type = 'time';
    input.min = '23:00';
    input.max = '01:00';
    input.value = '23:59';

    if (input.validity.valid && input.type === 'time') {
      // <input type=time> reversed range supported
    } else {
      // <input type=time> reversed range unsupported
    }

### Making times required

In addition, you can use the [`required`](../input#attr-required) attribute to make filling in the time mandatory. As a result, supporting browsers will display an error if you try to submit a time that is outside the set bounds, or an empty time field.

Let's look at an example; here we've set minimum and maximum times, and also made the field required:

    <form>
      <div>
        <label for="appt-time">Choose an appointment time (opening hours 12:00 to 18:00): </label>
        <input id="appt-time" type="time" name="appt-time"
               min="12:00" max="18:00" required>
        <span class="validity"></span>
      </div>
      <div>
          <input type="submit" value="Submit form">
      </div>
    </form>

If you try to submit the form with an incomplete time (or with a time outside the set bounds), the browser displays an error. Try playing with the example now:

Here's a screenshot for those of you who aren't using a browser that supports `time` inputs:

<img src="data:image/png;base64,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" width="560" height="112" />

**Important**: HTML form validation is *not* a substitute for scripts that ensure that the entered data is in the proper format. It's far too easy for someone to make adjustments to the HTML that allow them to bypass the validation, or to remove it entirely. It's also possible for someone to bypass your HTML entirely and submit the data directly to your server. If your server-side code fails to validate the data it receives, disaster could strike when improperly-formatted data is submitted (or data which is too large, of the wrong type, and so forth).

Handling browser support
------------------------

As mentioned above, Safari and a few other, less common, browsers don't yet support time inputs natively. In general, otherwise, support is good — especially on mobile platforms, which tend to have very nice user interfaces for specifying a time value. For example, the `time` picker on Chrome for Android looks like this:

<img src="data:image/png;base64,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" width="360" height="640" />

Browsers that don't support time inputs gracefully degrade to a text input, but this creates problems both in terms of consistency of user interface (the presented control will be different), and data handling.

The second problem is the more serious; as mentioned previously, `time` inputs' values are always normalized to the format `hh:mm` or `hh:mm:ss`. With a text input, on the other hand, by default the browser has no idea of what format the time should be in, and there are multiple ways in which people write times, such as:

-   `3.00 pm`
-   `3:00pm`
-   `15:00`
-   `3 o'clock in the afternoon`
-   etc.

One way around this is to put a [`pattern`](../input#attr-pattern) attribute on your `time` input. Even though the `time` input doesn't use it, the `text` input fallback will. For example, try viewing the following demo in a browser that doesn't support time inputs:

    <form>
      <div>
        <label for="appt-time">Choose an appointment time (opening hours 12:00 to 18:00): </label>
        <input id="appt-time" type="time" name="appt-time"
               min="12:00" max="18:00" required
               pattern="[0-9]{2}:[0-9]{2}">
        <span class="validity"></span>
      </div>
      <div>
          <input type="submit" value="Submit form">
      </div>
    </form>

If you try submitting it, you'll see that non-supporting browsers now display an error message (and highlight the input as invalid) if your entry doesn't match the pattern `nn:nn`, where `n` is a number from 0 to 9. Of course, this doesn't stop people from entering invalid times, or incorrectly formatted times that follow the pattern.

Then there's the problem of the user having no idea exactly what format the time is expected to be in.

The best way to deal with times in forms in a cross-browser way, for the time being, is to get the user to enter the hours and minutes (and seconds if required) in separate controls ([`<select>`](../select) elements are popular; see below for an example), or use JavaScript libraries such as the [jQuery timepicker plugin](https://timepicker.co/).

Examples
--------

In this example, we create two sets of interface elements for choosing times: a native picker created with `<input type="time">`, and a set of two [`<select>`](../select) elements for choosing hours/minutes in older browsers that don't support the native input.

The HTML looks like so:

    <form>
      <div class="nativeTimePicker">
        <label for="appt-time">Choose an appointment time (opening hours 12:00 to 18:00): </label>
          <input id="appt-time" type="time" name="appt-time"
                 min="12:00" max="18:00" required>
          <span class="validity"></span>
        </div>
      <p class="fallbackLabel">Choose an appointment time (opening hours 12:00 to 18:00):</p>
      <div class="fallbackTimePicker">
        <div>
          <span>
            <label for="hour">Hour:</label>
            <select id="hour" name="hour">
            </select>
          </span>
          <span>
            <label for="minute">Minute:</label>
            <select id="minute" name="minute">
            </select>
          </span>
        </div>
      </div>
    </form>

The hour and minutes values for their `<select>` elements are dynamically generated.

The other part of the code that may be of interest is the feature detection code — to detect whether the browser supports `<input type="time">`, we create a new [`<input>`](../input) element, try setting its `type` to `time`, then immediately check what its type is set to — non-supporting browsers will return `text`, because the `time` type falls back to type `text`. If `<input type="time">` is not supported, we hide the native picker and show the fallback picker UI ([`<select>`](../select)s) instead.

    // define variables
    var nativePicker = document.querySelector('.nativeTimePicker');
    var fallbackPicker = document.querySelector('.fallbackTimePicker');
    var fallbackLabel = document.querySelector('.fallbackLabel');

    var hourSelect = document.querySelector('#hour');
    var minuteSelect = document.querySelector('#minute');

    // hide fallback initially
    fallbackPicker.style.display = 'none';
    fallbackLabel.style.display = 'none';

    // test whether a new date input falls back to a text input or not
    var test = document.createElement('input');

    try {
      test.type = 'time';
    } catch (e) {
      console.log(e.description);
    }

    // if it does, run the code inside the if() {} block
    if(test.type === 'text') {
      // hide the native picker and show the fallback
      nativePicker.style.display = 'none';
      fallbackPicker.style.display = 'block';
      fallbackLabel.style.display = 'block';

      // populate the hours and minutes dynamically
      populateHours();
      populateMinutes();
    }

    function populateHours() {
      // populate the hours <select> with the 6 open hours of the day
      for(var i = 12; i <= 18; i++) {
        var option = document.createElement('option');
        option.textContent = i;
        hourSelect.appendChild(option);
      }
    }

    function populateMinutes() {
      // populate the minutes <select> with the 60 hours of each minute
      for(var i = 0; i <= 59; i++) {
        var option = document.createElement('option');
        option.textContent = (i < 10) ? ("0" + i) : i;
        minuteSelect.appendChild(option);
      }
    }

    // make it so that if the hour is 18, the minutes value is set to 00
    // — you can't select times past 18:00
     function setMinutesToZero() {
       if(hourSelect.value === '18') {
         minuteSelect.value = '00';
       }
     }

     hourSelect.onchange = setMinutesToZero;
     minuteSelect.onchange = setMinutesToZero;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comments</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#time-state-(type=time)">HTML Living Standard<br />
<span class="small">The definition of '&lt;input type="time"&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`time`

20

12

57

No

10

14.1

Yes

25

57

Yes

Yes

1.5

See also
--------

-   The generic [`<input>`](../input) element and the interface used to manipulate it, [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
-   [Date and time formats used in HTML](../../date_and_time_formats)
-   [Date and Time picker tutorial](https://developer.mozilla.org/en-US/docs/Learn/Forms/Basic_native_form_controls#date_and_time_picker)
-   `<input type="datetime-local">`, `<input type="date">`, `<input type="week">`, and `<input type="month">`
-   [Compatibility of CSS properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/time" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/time</a>
