PannerNode
==========

The `PannerNode` interface represents the position and behavior of an audio source signal in space. It is an [`AudioNode`](audionode) audio-processing module describing its position with right-hand Cartesian coordinates, its movement using a velocity vector and its directionality using a directionality cone.

A `PannerNode` always has exactly one input and one output: the input can be *mono* or *stereo* but the output is always *stereo* (2 channels); you can't have panning effects without at least two audio channels!

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAwMAAADhCAMAAACjmJkFAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAKdUExURf///////wAAAPn5+f////r8/RsbG/////////////////////z8/P///01NTQAAAFBQUP//7tra2tTU1FNTU93d3e///87OzoCAgeLi4nbB7eTk5O/KegAAgVxcXeHh4dfX138fAOvq6mVmZff394SEhNHR0be3t8vLy3x9ffr7+omJicjIyGFhYVdXV3BwcOjo6Gloaaampo+Pj8XFxZaWlmtrawoKCr3v//Dw8Ht7eXd3d/Ly87Ozs3R0dL+/v8LCwu/If5OTk+j///r//wAAI4yMjMOALGxubq2trf7++wAAPxQUFO3u7llZWbu7u///9fX//8Xj+YYdAOfl5SFzxdj8/4HE8P/3wJqamjAAMh4eHoYwAP/+1KqqqrCwsOzs7FcAAJ2dnQAAM2636p+goD4AAMb2/wAWhPjcpAYujLHq/wAAWlyi3anZ+P/6yCkoKZVDDDGAx//+3tWcSXgAAPjWkP//6P/vuu7CciIAAPzmugAAeTs8OyFyvL52EDEzNABsvcyNO9/+/4ejyOS0bQAAazIAAAAAS5nQ9WB5rUJqlkVFRffPhMKhmiVKYoSdurWYcUZpfWpxkJAvAGCMvf3sy9ejXKV7TGxaUXcoAOzVswBIlZunyYc9AEoAAPD/78elghUxaEYjAO/Rn3rI96K93m+QpgBbrGlyeqyohuLDmaleAEKV1jmHzyxQdnJHEwMvUrve+nyw29D4/1ghAHZzUlWW0z2BwTVmrI3K79WxjFc5KYienE91pWEzAI1sWJJ/bgAbdWwAAFBSYIZiLffLellegeHm8Z5pM51/bpC94qezuryRWt7FrKh9hiNaip6TY4Bkav/19ah1ba6aqmlUMwMhMdPo0394XAAkRsLWtL/Y4rW2mcHKpzQ4amEAAAANdFJOU9rQ265fjw5utKVyeVXR7vzGAAAgAElEQVR42uxc+0+b1xnuP3B05K2ypgiiplSV0h828UMnq+t+sGwrldEkGxpAGZaGzIxxiBmXAIEIFq4mzAmEO2XhEnKHkIQkpEnInVDaQJss67K069+y857bd3wDbFNtgfMKCXwu7/N+h/f5fM55vvO9g7Rp29n2jh4CbZoD2rRpDmjTpjmgTZvmgDZtmgPatGkOaNOmOaBNm+aANm2aA9q0aQ5o+/+3jz4AM1UWJNvxc3P8cuHK9FVUQfyPm7IN+oQD5jhFMoANLKL3+7/4yp4UtubAW2+FnRhsfs+uJDt6imcT5Ct3VVOeH1mA4n7cHAfW72PNtMUpkgFsYNZMyQHTChmLjnyUWryaA2+nOd97b6j8xw//kHRiVo+WrJ+v7Y9tMUnkIvfUn4EDGZnmOEUyANf6d3Kldw1u+9Naj11zYKfZM7+Z/KPPbpW7GFdKgSvvbEpQrrwNOOBejxaAut71y6auyqZNXI/mwPYzSBdT0fmr+D65b5qG8dR1Vj59D8/l1w3jN9+Q7Pj2OaknuTJ9xjFA75OuV0FUdr634VoXTZSH5NckqWnsa+Wuyo67wdu/5qVvhEjz4xOxUIMP8V/b7AKKOEZ35w3nl894z48yDlB/gw8bvG1IAUfWx71/uXYHKdHBRZEAnHfPOE7lAqqbocnr4OB1K3juhV9wwJS3n/6G0D0vb/AhMMLXHNjWHOjH3ZfwIYT2eRcfdLRCcb1v6lKfuRn3LOEgyQ7c3Uvq6zu/ewHNSL4cLkFWnLN4lc666w4voLpR0rG9Y4K7OnLUhvbh84+6pG/CEt9cWyyUqzL056Uv7QKKOEbNx6TzxobvLjVgNpuh/soO9AyTdgY4CmPv4pIjqEQHF0UCqCVQB4KAamdo4joEeLODYAaM74ELlEEQev0BCxuCCSN8zYFtzYHTY27U3IQ84yUkkwrYmpbcCCt8JaiuqEnW10BiB9x8mmzFXTRXiDVfIG0dFvJbNCVuPcUL0JIXwOoD5kIxUBW+s0iBgvn3vv3SeYvfho4wDjB/lHIR4FZSXbenSokO0MlPi9/NUTlaFDjFHDX2hY7gL1v5iBQS13QIlPA1B7Y1B/IO0cSrzSlFqP+QnBtb4XON38brXZVXEKqlN19I1QzyVyFLw/YOW9jRUEDaCVfEba3jIJ1hsALeKRaqYvyQCsU5wJ2b+qugBeUA80ezOgI8I0RytSUwYUTHOVDTIULlaFHgHNNYOkxiPCA5wIZACV9zYFtzQN58T+39N6b/+qIrNDEtdNHI602nc/b+6qbXIjjgN4s0LHNYasaWqip8XTKHSRZCiknfggMxUGSKQ2bxUVDCuamoCvKQrgeYP/TFo5GGAhUc/kT7/BNGdJwDhb6pXPGVRdGiwAWmst01TEjAOcCGQAk/BQ4kKb9w0SWOtJFIjknSoqWUhCJKKjLONuGA47OsrKxv5JYg3V6xGhwoOpmdldXXKjiQKdPQU3xnZrZmbDp0Q+UAvcMm4oCEQq5hHGiNgpKJCOnP9yeZv3Z87RMy+VHAedcJIzrOAVRWjOcZBxhaFHgGCAvWyJ3VmvJ8AU1R0+JAkvKLEF1ipY2EckySFi2lJBRRUtnC3iYcCIkhofdfZIUhyjA4kDerjpGShq7K+6Nnw+UvAu6I7wHLOhwIKaM/3VkVBWXcjPcr3wMWCKwJOfsjwCk3avwTRnSCA6huJYfmMkeLArd6o78HkLPRa5HQVelyIEn5pXq0hIoZUtpQazb9D60NmNf9Z6sWi4RSl3G2BwfK8EE5DsfEDLzFLxLTOXMhAQdQyxvvwULfmStIyWG+HojPAQOKdg9MSyiSBDMGB05XwV3QWA8U+gromlgBp9P6fWNuIzrJAbLUvgOIHC0KPOyNWg8ACOEAKSnzWtgQpDcXQvYk5ZcNxIzN2LNYuSQhBxLGsIWK0VvGgeonTXb0D7pBOAQ3XU/xbeR5UiXr2x1BhD6Ix4EwPmqr24MLVA5A7ygOnI0D5SJz0uYxCZV3BRWOVxmbM2Rd2y72hW7DnlAJSeGIuZAVH0IVZLJgRMc58L4Z1Td0ASpHiwKH1Xj1aMBsGmYbTp+SYFbK862hUtRCLp8OQZocSCS/lPX0NoAcgqbP4G4bYkqG61WQihkgULByIYOocoxrFZ/MXr5B3dwdAEWlSygjIGi8/h4/DfLurm9/uDdVqsBBNHdJo1IuthAkoZkYbiNkHENz2cYGu+FiU55k28lbbPelojj0Sbd5CJ96QDJB1FePOi7ePCb0AbqPjhkH6jsv2J0zXqMpVNbgUyN3pG+YxziOT8RA1eOT35Ms5lCoBV/04WPSeeH4tVsY82eQwN+MI7uTfFbAMzDpGrIo0UEt+Wn2Zvk6WgHVzdCir7OFdMSErE+O2uiW65usB2QBUTE+tYQdFjYEE0b4qXMgVn6xck2jsWHsEhk6pmSQ8KiYQULn5UIGUeWYdty2ggfYHGaIeCvsLODKCBU0Bpe8fbm8uykPz/WYFTgSjXOl+z/jxDMVWwiS0EwMt6qMo2gu29ga/25HzhO5CH1xjny6nPWbNvZVOvjytz12NPnrZVIl66u//qwvl850SQn0rPsnm9abTpDaNTLeoilUosnsi7mGb/Jr5Lg7Bsp1d2R3GzSmUMjU+24P70+dN77MPreWy/cuib+6r99tW7uugjeeWxtZhturjA5qyc/go93wGVAZWvR1unqz+l4/d7t65+k1rf1u93KQhrn844l8NgQfKeGnzIFY+cWK76A6suBoIRNyq+MgUzLIdw6IGdCHlwsZRJFjTP37yQyPKeSojDQJh0q5MkIFDRQmvnh302nGOAnH50JHMm1MbIEFGAtOcavKOIrmom2rzLmJNvYNC1Lzu2FvZzp+3klCfqHyBmga/XS5s0sqGXTqlZEpyqVMskf5s8R4gMpTXKIoI+x5J8hr3p1t7xpwfJGEwmKxBm1ZcIpbRcZRFCFt2tLhQKwmIjQNLn9IJUNwQMgiQiYx5BhT0SyqLuYccM40OSurhG7DMh7ymneXuzscjnLANJl9L8DFG2XPz3CrbF0oipA2bVvBAUMToTdkkut7uPwhlAzBAVGuaBViF6Dlce5Q6IbY4Pd7iguEbsNlFJ7XwpsCBxyoHsWnrvq5eKNsRhtuVQ4omos2bVvAAUMTofIcaBoLXP7gSobggCiPwwGPD+N5uZUb+imnlOs2TNBg85uFqO8BBmcjdVbvQZgLMfFG4YDhVuWAorlo05Y+BxRNhGoazWMToEFU+AqkkiE4IMrjcCDsDRruK4r/FjBz3YYJGtDOxbtLDnA4N32Q0IyO+JX1AA/OcKtwQFGEtGnbAg4o8osVL1BNY4jqEKVCydhFtSnSh5fH44A159wv5WM+rkpMFgFcGRni93a3cGtwgMPBM+UdNudMgIs3CgcMt6qMo2gu2rSlxoEE8ksY44sPQqXIUxy6hW8jrmQcLqFiBunDy4UMosoxYXgEaUD4bwH9kCsjTNPJwCeDvDsFVuGIjzKQYwidqNgC+gAPznCryjiK5qJNW2ocSCC/WAM/vcwGTWPw4dMeO2JKBrQDMQP6sHIhgyhyTMX48U9Nq95S4f9jWLByZYRqOqbep0HenQKrcODj8sjy6+duJraQzzw41a0q4xiaizZtqXEggW3qwZ24Rh8uZEuIrYRLya02bf8zDtQ6LD8HB5J1u7MtHDBvcWto87k5tqlzFeck8Z8Rp0K4u/UbpXtdqXPAmjIHynD3h5MNY8l13xguJbc72+K81yrN1lZ4hmU2tmlh5/nfJ4ElToVY4bnV2Q0apXtdaXAgda5dPoO9A0lGuQm4VNzubEvuu3wzramEWRLbtFEu/zZl4lQIdxdrcMQk7tGRNOco+jzxzuOAe+s5ELfps6Mp3ZyeJYJ8tm7kmgM70OhRCnnkIvIVVGD0PVPs2IWsRnHea+V5STpM3zeLl1n9cG8qm5WwzBKvxmpb/eOCOK4RcT4D5M1X7An31QUjgsv3vE+75IkS6E2jEidMhvFc7mqD8vosOH/CX51FD57QHhwIrnURjpjQRuydXuJkCo9Pc2AHGj1KYRy5iHgFFRKv2mLHLmQ1ivNeK08x9AuY5cus5hZ5Cctv+Wos794gP64ReT4DJMvDdC4UxgVGBGtXQ3uvGydKSG849Cs/l3/swzmLNwNuERwoSfzVWezgCekhgOBan8MRE9qIvdNLnEzh8WkO/Je9a/+N4rrCUpXkh7bLgglg87BdiB+YALaxAWPACyYtGPNwTQsR5S0gNSQYQyFgSIkjIKgQEglCUkiwUpIgakhRaZu1IlTJadr+0JZWqppWyf/Sueece++Zl1mDx87snGNhvLMze+/u3m/vzP32+77kFUopjOQi2GpL1bFpzdxuyudr1dL3amrcpTvGzMoZwH031RZ7hoHWWC+mtFzDrc8g2n7qtN6f3eQ9uDDNSELgaPUNf3Pb+XcsfS71xa6FzNtLW2eh8MQ5ghrC56okJnqnn7zCvbq0TFkwkKyCr04ZyUWI1RYOxYncbsrva3XlRPOBPf3azEp9lf30mdecLRYDyhpLaXVJruHRZxAGlnX8bf9el9rESkLg6JTtL0hDljnXzEpeZb29tHUWGko453DUkPmaGNupmXl1tbQLBhJ5bauGgktyEWC1RbILLi/3+1odeW6hM3K5mVV3et8RtMVSI8taY5Fcw6PP0BhIp+Ekx6pNrCSEHIZSrttTnZlKuwFpDFi7LmiPGjKyEb6T8eqi/o0aBvxkxvD4XOXqzmX2S5a9lh7LLslFgNUWyS5cGPD5Wm3Z8eHhjonczOrQwOTDxv6TWWORXMOjz7AY2LXPozYZxxUlKdtfHM9WaaV9jcg6S++hGzKyEWO9sgz/Vxjg/RsNDASQGcPi8ZOrO5fdL1nWQintW8UlF0FWWyi78M0DLl+r9Qc/7etymVml+rJ9XTS+e5k1Fsk1PPoMfT1wpnfgtlttYiQhBgP8NneFo3lgF5sHQM572z5XMw+Qp5cx1GL9Gw0MeMiMYfO5ytWdy+6nm12flPkAzpFdkosAqy2SXXAMBPhaHf7fno0uM6vU6dX0Hayp07g1Fsk1PPoMjYEX2nrOvMbUJkwSokeo67YfA9o6S2NAN+S6HtD2YXS4q3/fgOuBUfS50s0Og91XXNaFlJSCSy4CrLZIduHCgN/X6kjawQU3s0p1H199T88DzBpLyzXo2E2f9bvWhSa+fHwj64E6gitKUra/IRgw1ln67Ika0rKRNm0Apjy96HBu3TWMGEDvLE2/ULwIOl9pYiYw1CTM5wriStb/Y91vgB7hblncvwszRIxvl3nc7s+e+/xdLcMkQkQ1Df1x9iPehpoFu69EgACkFFxyEWC1RbIL5pYV5Gt1YI/iApiZFQxEXFg90cyssbRcg469kD5H+5BSZP3BaytsD9QRXFGCyLW3UVqyj3t7kXWWFp6YTsJzVRITtZU8vUiZ0sL7N3wYQO8sTb9QF9H5CoiZsFCTEJ8rjCtxjn9w6/jNlMsti3E6lCFifLv0424ZuPb12Q+0YpIIETi1dPqjPqSQt9GpI2D3lYyZQEkpuOQiyGoLZRfcLSvA16rlDbjLmlk5Jxd4OaCkG8way8g18NjDZ5ppH60Uufpem+3B284NriihDzFzW91/6N/N3NuLrLP0w9lOqueqJCZoAAaeXtqri/VvGDGA3lmafqGpCsgTJCtCQ02Cfa4wrsTZ7pyb4oqbcctijApNbca3Sz+uOkfsucaenzr5g8dz+qOWRJC30c22tCfJcjSqouwMb7nlGi0Hu/Lj2QZhALyzDP2iMaAWnOlCLCzUJNjnCuNKYEmAXj/jluVmVNTD2AQSetypzofNBf692Bby1FL9gWVB4G0005K49aFIatnqvaEYMHKNo+/uy18MgHeWl35B7wggZkJDTUJ8riCuBLZvcj7zuVuWm1HBy3ydQEKPu+z1e6kr1mUbCRG21Kx5G9bNqxXrKsRk7tHr6Bu/uxl4YpGnco3AdSHlneWlXxADQMyEhpqE+FxBXAk+Xvtkl1uWx79LPYxJIKENB65ffnvgju4ZESKcbiHehnXzB2ntdyz1aGdCH4Tov/JTrhG8Nnr0r6t/6KFfaB4AYuZ2iq3Kh2DAxaPcONsFnlwHrk92uWW5GRV8GJ1AYhzq0ukOy/wgIcIxQLwN76aU1OPzAwf29Bv6BeNFYHDBWXx4qEm4z1VPB5iRvny23+WWxRkVzBBJmQQSvXx86ZU2dpa20VwTawwgbyMYkBpODKB3lqZfKF4EBheSFaGhJsE+VxhX0vu+c0F1eP+PXW5Z3L8LM0SMb5fNtcqWlraZNSEkRDgGkLexGJB1IanHxwB6Z2k6g+JFkDwBsiI01CTY5wrjSsZdSt/9b/pOyuWWxTkdzBAxvl2GA2l3zu73kzZKEyLUNPxC3sbQGMruS95WqcfDgE4BITqD4kXI+QqImdBQk0CfK4wrGdf+27dmvOkMT+6WxTkdzBCxvl30uD37X6q6ukOvRBMhQk2rX5q30c1CdomU1GNfD3hQMYQHDIsDwRP1IXN54753Gy4nQtfjxGZLaiQwMBz1iBergAErivLX1ATYbBU2yEBNMAZa+la/V/mndH/oDgmw2aoqlHGaHxh4xC/2H/pjOn3xpUF2yH+bremCgfzAwGNVS6LfowmCAcFAwmtSWdDHQm4iD9pNSjAQ68oEYSBHkQfuJq+hYCDeVTErYGOOIg/cTUowEO9aNS9gY44iD9RjSAkG4l219QEbcxR5oB5DaqgYGGQZM/cVzvDEkPAaNIIkufX8zqCtOYo8QI8hNWQMhNNZuTNd4Ykh4TVoBElya3lt4OYcRR5KjyGv4Uhg4Ij3Gz3hiSHhFRhB8jDXrPx31Zq3Knh7jiIPss+VGhoGQr+Dv749BANfTBuG9YfACJKHuWblv6vWrIqAjTmKPHC3G5/vlaE+NAyQX5VOINEmWr/+1a6Pf4kYABqGJZTcVyEhRMuApdYK5ZnlT0FB+oaSREyIiiJ2eAQJNYiHg2uW9eIC0ufWZeXvdQ5aQlctbJrFm+QROVRWF7AxR5EH7nZF9NVDxQD5VZkEEjTR6j7+4NZxFHGhQxZLKIGQEKRl0FJrxbETzS3+FBR01qIkERui8smbE10RJNAgHQ6uWdaLC0iffzp/bzq7EVqC+4kRYvEmeUQOlZX7t+Uq8sDdfvrnezLUh4YBG1uCCSRootXzQnPqGGIAaZiUTSiBkBCkZdBSS/s/ulNQ8DidJGJCVJwR7Y4gMa5dzuHKNYt5cQHp053el7rw+pfQErhqESPE4k3yiBwqLMllrxUymIcTAza2BBI+0OwK+BgyIENFfMomlKDJMNAyX4KllsaAOwUFj6MkkV5N8Chih0eQMNcuMg5nXlxA+hwaeDHV00HmXc79mhFi8SZ5RA6JfGCU1oXUoLUJJCBupwyRFNEw/H4wHyZaBiy10D/em4JCzlqYJNLLCR5vBInCgD2ceXEh6dP3aosz7I15lwkssfEm+UMOVRVWyTgdLQywhA+FgfbJZm0UHbJ4AggE7yAtA5ZauM7pTUGxgSIqCoUTPN4IEqdBdjjz4kLS5/SJLTv6rXmXCSyx8Sb5Qw5tl69OjxoGeMIHzAM/YvPAQmt4ZTBgaJkbZ7swVsSbgkLOWpgk0ssJHm8EiXJZtIczLy4kfbpXfw1TijLvApNTbJrZ2ucPOSTygdHDAE/4UBh4H07f7fWAKwFEJTRbWqanQ8WE+FNQyGkXk0R6eYiKN4IELKjN4cyLC66p+w8NnERSrqdDTSe6aRcG8oUcKi+TYTpaGOAJH2pQqavM03pd6FNreEUYaCNaBi212pyt/hQUpG90kggPUfFGkDgNmsM/5F5cSPqkfp6+o827FKNHjBDDAJl1vfOH2L9FGcHAKGAAFRk84UOZaG26fvf32swWaBieAKJCQpCWQUsttTUgBQWdtShJhIeoeCNInAb14co1y3pxIekDYCTzLnU/MUIs3oQ4pIETsZcaB8oHpKLFgE4GYQkfYKLV/a+aj/5Oiy2KhuEJICokBGkZtNSCrf4UFHLWwiQRHqLijSBRDZIbF7hm2XQT5IZUmge1BPcjI8TiTXC/9W/F/7o4UD4gFS0G4lCDuG5B5RFjFCgfkEo8Bsa1dyXmLdq5U4apYMBXV9/BSMREVH2tDFPBgP9MKH05OW9RmHxAKuHXAwmqQPmAlGAgQVWWkdcgBhioLZdXMjoMyIsbBwwsl8u26Co3+YDUaM8DsoQdIQbWyGsQAwwInR9diXwgHhiYJF/riqzWyFenY4EBSYmIrkrktY0FBkTyGl2JfCAmGJD1u8hK5AMxwYBwmZGVrDfEBANCEERWIh+ICQaEIIis5KWNCQZkwo6sRD4QEwwIQRBZiXwgJhgQgiCyEvlATDAgBEFkJUtuccGAEARRlcgH4oIB+bSKDAPy6RITDAhBEFUVTpDXIB4YkFXsyDCwXV6DeGBACIKISuQDscGAEAQRVYOsOscFAyNFEKz5+P79j55J0Bsk8oHYYGCECIKt2eyDB9ns4uS8QSIfiA8GRmQJrzybTTuVzf4lMW9QnWAgNhgYEYLgFwABBwTJsVqUxYb4YGBECILsXcTAxWzRFKjq6UOqGC4zinwgPhiIlCBoGF+xs2zlnPOtCxADm7Otm0+NWVm/aklTJpNpyjTZWuepCl7rCrbnUMH4qXZqw5SHVPXgVfUNe12lhhUD0czZBTVjT3bqkW/rYnZz6wLYuqB188mxS3ePLzLDsKioBGuCqgJVpVDj/VVuapKnKqGetVWnqqL2IbWtIqSWQE3aEAqxsHq+3kKwekputcEU/1vVI8FQMJBjRUQQNG12Df5WmgYub51X2Dh3fvGYk52EhgULWjtPPr1096TxatTD+EcUWCgYNBAeyj1IoNEPPxoFbiBU8l0qfZCpZJton8Hq2aCq89T3l+P/GVVbOd628lplapu7lvCqaMoULF5cLcM+GgxERRBM72QQ6Lz/H+f3+WxW3fNM0+55jTUz1s6ZPWP+XB8aGnc7A7LcGeYFDBN6hijhU0UQRkrDpwzXbMHgkMP49g1wV2Xgh414qFn19u9MnUUjRxx2zHQVn0GBKXqOzvPFs7V1JVNk4EeBgcgIgul2JuisrvjWJ9ls9rKd0Aua6gsbZxc//fSctcUKC42LZjM0tG7uPLl2UW1dHXyCwygpZZjQVVTiqQkGHxobHB9Bp1XlnnMrBRb140ZLwMzxMNyU7fTjxweESgYG1qlSDxoIDBvWNDUICqLAQGQEQZOGwKnqbz/11JNffeWliasy2+oXzZ09dsxYBwrFxbNr5s9dumhm4UxCA102dJ4vLlzVlFEjqBLHCw4TNj5g9E8oCSx2XuX8wC8zeSBE1M9gMOFnXeWTgi9DfFVZVht4HmX38EwCvoGvR75+XkVFRVPWlGdE8xQBBqIjCM4TBBqe/O53nngi5KKuoal+1qKaYgcIDhIcKMyeUbNy7tLGmTMLy2bNLD5/6v/snctu4koXhc+vf3DOGYARF+EIKUbhGjtcHbC4IwYoIEgmmSCkECEx5wWQ8gA89HG5ynZdjUNMdzrYPekrncD+vPbaq6q8dxql9ccxp21eRmPAAyonVERu6ZBCAQrHuaxfiABJxdkrG/cmg9tx2T/kgYAO7j1fVPjm1+waZrMduus/hLUfPAMXCgge9rkmRKCv/j8fmc89/q4a37QK3UrV5CAWQ6KQa9soFLSp3ns+fqwxGqJtvVQCOEB9QDzYQGTZjpoEIoORQUGhKJ5cMAZERIj8whLit/JvnMq3RkLWBXOS92UxdMbBM3CRQfbbWlpn+gCBQz6Sn/v5J/lxU79vW4KAkdCwUAAsQBi0WpU00bFaCwQIYh6yRO2m2ButQmMhFgs/dCA+5AcOH/zS51Q+Xvig8sHVsa78Y1j8gTNwgYBAW0gfwGUsLARU/6NtNT5YFWpIEKKQhGcHhWGvi1gwYdCn7SRhG8BIaTCwcBjhOEAgikwZZoVYKBy5uLnx9BoMHVk5K2SE+O+87vlu5Xf64Mr38/l8/S6s/qAZCDogUHOGdISCvZYOamT+2XSnAwQhd5u0OIgiElwUTFnoOiwAGCaFnGmiF7iJvm8OSjYN40fIQ9lXP+6FhNub26keAUfKHt6Cf1yUWTDo2z6/9u/Y2gelb1+q+hJWf9AMBBsQLKOGcWtX/eKoRtSzNg3kHwcteZiDjVHUJgGKgo2CJQuWYbBhmNxXaBNdeAPaAHkYjZ1+qczlwQMIwmn7wKIsE2iQ7VdGVP2o/CkATAQABf28ahKgquF5FYEzEGRAED9Ii3v3hh5V53/9Mz/71TrjlSa7gmA7ZpOEZ0ACRAHJgqULiAUThknvljLRDX0GwlfIA1IICwh3xOQ9pLepiIuwUHAsxjKDBcaLW/z24kFY/XT5YxJg/gQiEDJwAQYCCwhGe2mNH7LZVyP/+/erndWj6RB6uaojCAQJNgpWh8RloTUZJmkTPZk5OCCBGMH8wQUCI6JIMsGlghlpKumNoxbUkqA6deu/W9L13yHqv++UP0RADU1x8AwEFBBsF9J+RH+V/wby0sAhyE+5pAuCSwJoj3AUgCzYLGiABQhDq9WatmOkia4Ot5CGAdYvQUP9iFYZCXomTyZwqSCEgm99rfp/ZwUAtj+OC0AAqPOQgQswEEhA0F1IhzhzE/8nQKsdH2+nBawzskEAJGCi4KAAZQHqQsGGAdJgmmjSNpgmGoeBocGaMaFFE0VPILJCkaBJYDhgJkB51wQgAiLmj3nIQPAMfD0gyN8aRpR1FfP8PODvWlWyD6VttxLDQMBEwWHBkgUEg0WDNUjCcLDEwaThnrINx0qh+WaLQ8k1DwiJsbvsp+yoBBcKrk4QM1ERCxgJHVcGkAaAIVvIQPAMfDUgqB8lo8EbgF5oybuaSo83eg+zCA4ISYwEJAsNCgWSBR25hsBt/jMAABU8SURBVNaETKL3h2hbhwuaXXWAQLzwgcBVosgHggHB9gpeHCBFgEpgqoBpu8LqD5yBrwUE6Q9p8eu3zqrL1MN4dv/0TCmCNUN1NQGiUAEdEpwhIRQwFjRHFwAMJg16jc7eai200J9DhCMRDhDlMukjikIQcA6QHjgYYBCgoRC6zHtOWP2BM/CVgGCwlta/7Zx9QWdk90bQKCBRQChgLCAUMMeAsWC2Sa2V1iYXsB6eu9umGAfbQyCFsBdJu1k1uXiDxcChgIIAzoUABSBwVMLiD56B8wMCfSHty6I/nP8qENKPA7YzchyzTULVIcFpkCznjKwzHwWLhdZqVahQtuFWhvvBTuJgy4PFgr3sO4uv+rYZeGUY6Hcwd2w7gkgYD1yCgTMDgidDOoi3dMx/4ZuhdlJlszPKPfMVwXXMiAQXBcRCz2VBZlhwhMGkodVlsjetSWsD2yvZAyZoGVwQIAUMA7YlwEek9lgoEh7pfgkGzgkI+knDqH6rsxNVJVF+2XZZDmgSAAouCZZXsBokKAvOSNVCwWIBwDDVKWloDekFrE+6DcOMhWGEL10iSUAgoG4IMWC3QlAGVFcGlvmw+C/AwOcDAuUgGcPv+LaAzqik1zidkQNC0iXB8cw5a5bKQcGZIhW0AhcGkwb9icneVpQ0YKGDu0KD3BNnkeCCgLqhPlorhOyAOo+Ee2guwsBnA4LHvbT4xqfnqO9x0yKYnVGS4YBLAuYUoCjYthmxQMOAK8MEl4aV1mCytx2EYeNm0S9sc1TEmiNXEixBcMUgtAOXZOBzAUFzLa2//wOc1JtEujTpVqM8EPgkIFFw+yOkCgQKlDCQyuDAsJLp7C2nvcEOiW6OTkgCBoLFQSrcT3wRBj4TEBQW0kfiD3mP1I5ShIKQ5HCAuQQhCXiDJGKBsgxEm7SiTbS17+1Eb0QqAmyN3mFnlA9boQsx4DsgUCuGcfzDtjGpN9niTK8l+YLAGma3O7JRsBskSha6PBQ4umCCsN1ud7tVr0qnDU2eW/YUhHIoA5dhwGdAsDwaRuWPPPJPXabSD837dpUvCDwSKBQ4stATtEiMLEAQLA52O3DQXItMokGjNBBaBOeQLSAI+URY+RdiwE9AkP2QFn/0o1X6mXj6ZVWrxsQgCNqjW0oVXBT8yIKTL1iCYHMAQoXZbAJoIBulkUdjVB+Hp45eioHTAcHLXlrvfsDb1lcS5eZ9w0MQMBAcEvii4IECIQs4B44guBxAq6yDdRk2DbBRYmOEot98LKGGDHzyOhUQrBbS/ufM5PqZVHq0hYJwmgNueyRGYYhQwENnjdy9QAmCNTx1R0abaSP64Z45+XGsaCUkCKmS39J+XE/VkIFPXd4BQc+QDj/uedOmIKS9HYIIhSq/PyJ9s+0WyNUXliJAr7yyQXA5oEOEjZazRkq2bYg2dku/397BbFz7IQOfuDwCgvyzYcR+6LuZf00lRtvebUw0MvLQBHeQylMFrENyFmoTi5Awh+ANgjUymskVmwbQKB1z09GJFRNbcN79cHltDHyhUIUBwetRMto/W1X7mWxxoLWt2Wk06pMEtBiVFQWwFM92zfiOBWpXpw+DwEQIxc2d+UmtalGbBvhInzL341GsYy6NxutVMZB/O//FBAEB2B4zvQZzpb4r2fGue0oQuCSINAGRQC7R/pw/IOTgcUas0VXHegNow74LaUj2dsR2bvQIIOM2dUUMlAtfWFDICwg2a2m9uaJJWz4TT5SmpwWBBkFIAr4mlWiLOHJwuisapLk3fFVOlAq3R3uktNgfnuXZq8OA+VvJxNUwsJXL578aGxBMF9JHOnJtFxCExKxbSSZPgiCQBJwEPgf3+CFIvruiR9G4U3dnepnZfRU9BU7FHwV3fLgOBjqyvD3/1aiAQG0b0vE1cqVXvq4kRq0GKOhTHHhpwjO5cU3YFk3dE5DEXdGoJFL5AW+eEX8gn4V4SF8DA2PzPT1/LQkREPRjhvF87Ts1Oko8MSvkorHTgiDQBDEGjBxowjQZdUWlN+FG+neZ91EN8echHrWfufeMZmBiMnB+jIUFBKmDZPQi4QUE4U6JZ7dDX50RBQJDAQ+DruAIMKYr2mw9RLnAOWtFXdj1H9V+7hIjioE6COcnZ7+aExCM99JiFVY/Lgh1JT722xkRG/mRNWC8QbvmNkXeJhnJwds24zGf3nICzh6sfz37oz8aioESYEA+u4VHAcFuLe2p0+3//uu3f6d/fwMQMqn4ppCL+e+MKH9ccdIDUgy8ogMnSV6lvSKaNDvYHhvrmB7/8bcnqjSnFgNnb+/q6GBAupA+4ifnT99gBPabOqOlCcJuWKkm/QxPaSGo4MFBm3TIXsmBSYEgBnOno8yJQ7NU5BousjBSFgLyFwItsD0mugxbnxNXv36Telw1TjkEsRJQGxEEyykwCnZ6+kRQrzev9MMgGdi8xfOR5cPkXP7vjpKRC9em+7xd9OtKaqB5zYzwFRVkcpbDIMCOsRC2RFs9c+pzGWghA+YFYnTzbqCeZwgSH9KiENb25zqjzquiNHs5niKwK01tY8xsxHmqea8pak1PP5iePx29OgbAJdzk1fF+i0prad0Mi/qszuj9VSm12lVaEJwdOE5m9kwMiPgb9vGWCGHQ0jI+vozCKGTAk4H6zHNk2lpI+/BA+y91Ru8ZpcmmaaQS4AtMxfuTu9SwdNL0dcb0thUy4MGA0pS91hENDekQnmMcRGd0l3lY1eiREbOkzpkSeVDgbLvR9Ka/IUVaDhkQMhDfgmGRyFPlq4aR7IcFHJggLOuZDWOVydUTRGhW8aRA65Z8Ln7hTEdDBpDVbVkDU0GnkzlIRi2s3KBB6Ly/lldDShDo04vwOREem+EYFLS6b6t7pdNRPzqQ2pkIaFwZKO+lhR6W7GU4MDujegk4BPpZUawa3PITg9790P/e4audjvrzAwNZfuH89mwtrQdhsV64M7pLb3vVJP2oKK4a0HLQ7ZY/06Re6XTUFwPZt1aBfS+1q9we83sE4T/2zvytqSuN4z/OT8fjVSfyMMRWcJxxK43zlIBVO2mSp2nApwGqQA0dIciqIIvsirKjUkAQFFFAUVFwt+q4W3HruFTH6cw4M//LnDX33uQGE0itwnmfR+He8573AHm/Z7v3fu6a8D+kGGbM1BKC4tqZpwxs6RsCu2CpsTu6mLy9RipM0vLHp6VHvqJ9rZv47+wZtTVXpxlvMm0EooEvQ2bN9ezuFxuMcI94q9tbFcKG8I2fRswZXwfyhmlU5Oq5ge5UeO+OJjeRe6cvzg/VzFR0umTTOu1gqWmnJ/7rekY16XVa8SbVRgAaQBIAMeqthZgZRuM88SKTt24LVsZs+Co9aub4AwKWAdLAqpiA71rx3h21f/hhz6b/LlzjWwMNP5i9CxxogCjuzfCv1dJc787cM2qYXucZL6A2JqcBLAG1zdoG41aIhPzVBoSVMWuWf2qY4/XKNPlVacuWrZgbM4H7tjR3Rx9k61CyH9PydySGagdyJB7zv9UH+ng/fHSTamNSGvCSwGdbYFy6SMVfeUBAQvgq3abx7kCigyXhE7xeo7U7irpgIDlPnIO3UNcs7YdHLtDzI0ddJ3pDQc6ueMfz/9w4ksWLhm7Asx2V53cNvMpHB0fhbjNwPH+CquMsTn2JXIZu6YaOWvdZSLh/3vwZjuW7HXEk5Eeiskplj+HZF9k6B4mHgq+7jv7LAryNnBPouxakiaewzfDwUvA14CmB9PVwi3jB+bsxIKARYeXyJYaZshLId/NSNkx4mqq1O0o00AV3n4KbAfjCdfN2Yx0+XVX506lKmAQqqs1SIjzbrmNF5ZlHTnUOZp6tl7ZmIKe+U03DFuSwuwNXRxN4HCS3qumnFyQcPHH3yX1XZ4LsiCIhPxqVVqqxtt+HuTocjwTXPd79v/5hC2/DBGNvnkPLhwZY/xjuMwddAx4SWBQHt80S2feOCWH2RoOBKiFidcrcmJWTuHlda3eUaOBwXzyo2Q5S+1EeNpE9otpsM6hAGkDF0mGU+7yoZBPqiu1onoIXC7VoWm+y5vHqqGB0JxLUmZJqM1JCfGraFbznkx0vO1KB0ai0UkFmBijrRRogC3DWz1fozbwNE2wB5d9ES11rkWtL0OdCKgksnmc0zhDvL3knlwhobkTfQTzZhzc0dkeJBhJxp70WlMaiiUoX7tClriIACvqpBpxnAC9yFG5ni2X0jzilpoXy6sh6qs0FmdcKcYVN60qteSzfuSOOxDXAKplw4JJsrAEaHFurXsfaAGFoDEhGGpif4Xt9MnENKCXw8R5oNIjHY6a6adw7SjSA94VwPsK9i/4NSZY7UdZKKOfCaDbyIprFXAPMiVfHm0DWaKSWw7GLQr53RYfh9KYqUjhyDfA2Y6PJmpjEIxKRBg03cmUNoDU71oDzNChOC7YGFBJYuAPGLREZMvVN495RlQastoiIiL8Bmv40BbkGaBHNYq6B+dRJoYHUtGMluQPONkNERGcdTl8537mjhwbC9GZyfcBdXNwL957LljWgJxpA06mEnuZLwdWALIFV6+H6b0V+TItplffuqEoDzfzSleRc6zEO0CLSo7s1kHjFcxxwFF4dLZIST9PQuIun854rvscBl2IcwMFNrjzVXIhpIDUTwovB3Rt1S+DzOLhFvMpzutgffzueBnJgHtfAYTKDT3JnKytyFO6UNUAOCjKTFBoAJa8zk+yjw4BOjNh6QOXooYFWl2I9sJOsxnWgwnscaHXlT+xX9qkBLoFII9z2O5Ea09iUGii+t90C/m4hudyItyNlDfCiHty342tq+Cw+6InNUmqgFKJFQIMV5esCpKGrpIF4laOHBgr6N6PpD53/k+AVjWb7KD4+ptKAKfb47EfB1ACVwII5RuNH4p6I6W0V1WaA9+FBDeqEG2DbZdJ5g+T+85chDCU7+biUFxWkNa/YPeC07hpAZ1PTmi/Dq3J1gHv7XB3KaevJ79FxCdx74FoYbMtXOrJG3ZVq4d7bUE+uD5DgObDtZ3zM2sA/XzlE4wC+sWlf8DRAJPDBNmhcLXJgulvVIQuwf5cAwMHj6GgkIrKe3tpQ9dJw/FkCLial7qLul1HtloMHdsXjs913xtqV1dFk6Tv8tfhHWyeuNGg4mSB1jOUrHVmj7kqOjojOfz2JJ8ck+MiBh+gYsDbwz1f2j3UF/btWSk/xvCk4GsASWLoFxmk8ZB3z5zUiLYQxs4xTZn8L7SvaMOE7TdGSIkgaQBJYvh6u10YurgpJWSqmR8LeuWUL1kCpNTo4GvgyJDIO7vDFmg/HDxcvny0ulwl7pywH7l44WNmnC4oGvt1hhHvCfVdZQh6x//00AbIKe19s5Ch0TeSWOQ0NREHjsnE7+c9DmH0SLv7wwt5/89bAJ3tCxrU/8XFglpgOCZt6GnCEb7C8qcbXZD2wUAhA2FTUQPddm62z7g01/hKSslRQ5YRNTQ1Ir2xRNtsbrrTFfCZWAcKmrAaqIm2HOmyd68RfRdh01cCQ7eSlHJvtgvirCNMwH5wtpbV6U1LsCxZY/ItvJ0tMu2W8RpVILftTGKu6IiY9mrwGBokGovLFxy1MSwPz3/iQlklv9hIOhARI8ebwh/GFXvJQpc9GVUit5KYTq1SBfdK+AtDAdToOCA0Im4AGMCkrzIsCJDmHP+iA2/3SAMzgj+D4alSF1KryvD/OJ+3Lfw3Yr9ts0UgDLeLjDups8zdTRgPjMq0wKSvMi5ZFcronNssvDeSavTQwzlPyD6r9GV78IHGp50KdYhz4ZZdc752V3UFd4uA+C6jqrOOcLcrHUoO1QBUmZYX98KLyfL6SxEVyOic2q/tOpasecB6WG59FHWko5xhsof5l++Fr/Mwyo3ixBnFCv8I3WcMd9eho5IZrrAVQ3BZhdV1UcLlk3hYmccXzgP7MhTrFekCYWgNbr4Cy3sY60NA4wDhb5ZSPpQJrAdCNSVmtMPYJntbLJC6S06Wx0TnftO+H+ZyH5cZnUUcSasB5tXCY+tfA9vvImVO8WIM42tYMR2Hzxvt/RRoYOte86IKd4rYIq6tFweWSeVuYxGVhAf3QABoDokfQmkB88sLcVjMMCjKt0egrZ14xPpYKrAUoKcsEr+HHGhVn6VyoOYvISeZhqZFdJJTkPBPmysP+BKrl3O6meLEG6eqgIJPPbVrZxKtCb6asLpnLpeBtYRIXD+iHBlJf2k5G2jp14oMXJi80G82t1sokKXEzY145GB9LCdYCNAM57kpxFq2Jw9ma2J4o87DUyC4SCmV/2b0zDqQBBtUaYBQv3iDTQP9m9pPxBXirXiezumhgBW+LkOhoQLM/k1W0KBbLAWEqy7FGl/TdL0K9KnvGXWJ8LCVYy60BirtSnEUrXbo3evDugcokNw9LjeyidCGU/SWNdV1FHKo1wLlbrEGW0F9AujagGqC4LZnVxX5GmbdFNRCtSa7WXLA9S0lPEB+7MOXkIO3a6OmSvqHmS+78onwsJVjLrQGKeFCcRePAAM69Bnh+BYVQqDSg4HJhDZQ3XSxcS5PbpB9gFC/eIEtox36YW8cbZLgtNasLBZZ5W5w8gSldfm9a2MXnLkyxt1h4q/dY66YXaAHANMD4WEqwlqcG5LNsr1NCs3F7V6iXBhiXi2sAjB65XUSfDA5D4wClePEGuSMYairiDTLclszqYoFl3hYZB2hA/zUgTJjSal+78pIzj57hjCHOx1KCtTw0oDjLNJCcmUTWxB4aYI6yBkohvErJW7XZA4zixRt0awDU5rJun+O25PWAm8uVr6jCAgoNCJuYtcJqc9l8NI/h+cX4WCqwFqCkLJbiirNMA2VbM1DCe82FmKOsAbR8KCLkrdR7RW6KF2uQJrTjEQA1ffFMAwy3xVldCk4v523hK3s84NBYltCAsMCtvGnYYh9FS1LOvGJ8LBVYC2cgbMvnuCv5rLSVkLXso1ZDEwVyYQcPZBc5pJ4NeCndA/feRrMbTvHiQC5yfaAcA7bI1hCOxXBblNWl4HLJvC1M4opnAXtgqNCAsMBNwkysZ+06GZRF+VhqsBby6xjLZ7grJYnrOp2UlP04p/7ZBc7D8kB20VDEs/g5/n/wo4f4DKN4uYFcuE3H9QPz6skQ030ItcBwW4TVJXO5lLwtTOJiAXO039QkNCDslzV7gJ7B2JMJjLclNCBs6pkpIN6W0ICwqWeB8baEBoRNQQuItyU0IGy6m9CAMKEBYcKEBoT9v306EAAAAAAQ5G89yOUQDoAD4AA4AA6AA3ATSRO50CgYONwAAAAASUVORK5CYII=" alt="The PannerNode brings a spatial position and velocity and a directionality for a given signal." width="771" height="225" />

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count mode</td><td><code>"clamped-max"</code></td></tr><tr class="even"><td>Channel count</td><td><code>2</code></td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

Constructor
-----------

[`PannerNode.PannerNode`](pannernode/pannernode)  
Creates a new `PannerNode` object instance.

Properties
----------

*Inherits properties from its parent, [`AudioNode`](audionode)*.

The orientation and position value are set and retrieved using different syntaxes, since they're stored as [`AudioParam`](audioparam) values. Retrieval is done by accessing, for example, `PannerNode.positionX`. While setting the same property is done with `PannerNode.positionX.value`. This is why these values are not marked read only, which is how they appear in the WebIDL.

[`PannerNode.coneInnerAngle`](pannernode/coneinnerangle)  
Is a double value describing the angle, in degrees, of a cone inside of which there will be no volume reduction.

[`PannerNode.coneOuterAngle`](pannernode/coneouterangle)  
A double value describing the angle, in degrees, of a cone outside of which the volume will be reduced by a constant value, defined by the `coneOuterGain` attribute.

[`PannerNode.coneOuterGain`](pannernode/coneoutergain)  
A double value describing the amount of volume reduction outside the cone defined by the `coneOuterAngle` attribute. Its default value is `0`, meaning that no sound can be heard.

[`PannerNode.distanceModel`](pannernode/distancemodel)  
An enumerated value determining which algorithm to use to reduce the volume of the audio source as it moves away from the listener. Possible values are `"linear"`, `"inverse"` and `"exponential"`. The default value is `"inverse"`.

[`PannerNode.maxDistance`](pannernode/maxdistance)  
A double value representing the maximum distance between the audio source and the listener, after which the volume is not reduced any further.

[`PannerNode.orientationX`](pannernode/orientationx)  
Represents the horizontal position of the audio source's vector in a right-hand cartesian coordinate system. While this [`AudioParam`](audioparam) cannot be directly changed, its value can be altered using its [`value`](audioparam/value) property. The default is value is 1.

[`PannerNode.orientationY`](pannernode/orientationy)  
Represents the vertical position of the audio source's vector in a right-hand cartesian coordinate system. The default is 0. While this [`AudioParam`](audioparam) cannot be directly changed, its value can be altered using its [`value`](audioparam/value) property. The default is value is 0.

[`PannerNode.orientationZ`](pannernode/orientationz)  
Represents the longitudinal (back and forth) position of the audio source's vector in a right-hand cartesian coordinate system. The default is 0. While this [`AudioParam`](audioparam) cannot be directly changed, its value can be altered using its [`value`](audioparam/value) property. The default is value is 0.

[`PannerNode.panningModel`](pannernode/panningmodel)  
An enumerated value determining which spatialisation algorithm to use to position the audio in 3D space.

[`PannerNode.positionX`](pannernode/positionx)  
Represents the horizontal position of the audio in a right-hand cartesian coordinate system. The default is 0. While this [`AudioParam`](audioparam) cannot be directly changed, its value can be altered using its [`value`](audioparam/value) property. The default is value is 0.

[`PannerNode.positionY`](pannernode/positiony)  
Represents the vertical position of the audio in a right-hand cartesian coordinate system. The default is 0. While this [`AudioParam`](audioparam) cannot be directly changed, its value can be altered using its [`value`](audioparam/value) property. The default is value is 0.

[`PannerNode.positionZ`](pannernode/positionz)  
Represents the longitudinal (back and forth) position of the audio in a right-hand cartesian coordinate system. The default is 0. While this [`AudioParam`](audioparam) cannot be directly changed, its value can be altered using its [`value`](audioparam/value) property. The default is value is 0.

[`PannerNode.refDistance`](pannernode/refdistance)  
A double value representing the reference distance for reducing volume as the audio source moves further from the listener. For distances greater than this the volume will be reduced based on `rolloffFactor` and `distanceModel`.

[`PannerNode.rolloffFactor`](pannernode/rollofffactor)  
A double value describing how quickly the volume is reduced as the source moves away from the listener. This value is used by all distance models.

Methods
-------

*Inherits methods from its parent, [`AudioNode`](audionode)*.

 [`PannerNode.setPosition()`](pannernode/setposition) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Defines the position of the audio source relative to the listener (represented by an [`AudioListener`](audiolistener) object stored in the [`BaseAudioContext.listener`](baseaudiocontext/listener) attribute.)

 [`PannerNode.setOrientation()`](pannernode/setorientation) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Defines the direction the audio source is playing in.

 [`PannerNode.setVelocity()`](pannernode/setvelocity) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Defines the velocity vector of the audio source — how fast it is moving and in what direction. In a previous version of the specification, the [`PannerNode`](pannernode) had a velocity that could pitch up or down [`AudioBufferSourceNode`](audiobuffersourcenode)s connected downstream. This feature was not clearly specified and had a number of issues, so it was removed from the specification.

Examples
--------

In the following example, you can see an example of how the `createPanner()` method, [`AudioListener`](audiolistener) and [`PannerNode`](pannernode) would be used to control audio spatialisation. Generally you will define the position in 3D space that your audio listener and panner (source) occupy initially, and then update the position of one or both of these as the application is used. You might be moving a character around inside a game world for example, and wanting delivery of audio to change realistically as your character moves closer to or further away from a music player such as a stereo. In the example you can see this being controlled by the functions `moveRight()`, `moveLeft()`, etc., which set new values for the panner position via the `PositionPanner()` function.

To see a complete implementation, check out our [panner-node example](https://mdn.github.io/webaudio-examples/panner-node/) ([view the source code](https://github.com/mdn/webaudio-examples/tree/master/panner-node)) — this demo transports you to the 2.5D "Room of metal", where you can play a track on a boom box and then walk around the boom box to see how the sound changes!

Note how we have used some feature detection to either give the browser the newer property values (like [`AudioListener.forwardX`](audiolistener/forwardx)) for setting position, etc. if it supports those, or older methods (like [`AudioListener.setOrientation()`](audiolistener/setorientation)) if it still supports those but not the new properties.

    // set up listener and panner position information
    var WIDTH = window.innerWidth;
    var HEIGHT = window.innerHeight;

    var xPos = Math.floor(WIDTH/2);
    var yPos = Math.floor(HEIGHT/2);
    var zPos = 295;

    // define other variables

    var AudioContext = window.AudioContext || window.webkitAudioContext;
    var audioCtx = new AudioContext();

    var panner = audioCtx.createPanner();
    panner.panningModel = 'HRTF';
    panner.distanceModel = 'inverse';
    panner.refDistance = 1;
    panner.maxDistance = 10000;
    panner.rolloffFactor = 1;
    panner.coneInnerAngle = 360;
    panner.coneOuterAngle = 0;
    panner.coneOuterGain = 0;

    if(panner.orientationX) {
      panner.orientationX.setValueAtTime(1, audioCtx.currentTime);
      panner.orientationY.setValueAtTime(0, audioCtx.currentTime);
      panner.orientationZ.setValueAtTime(0, audioCtx.currentTime);
    } else {
      panner.setOrientation(1,0,0);
    }

    var listener = audioCtx.listener;

    if(listener.forwardX) {
      listener.forwardX.setValueAtTime(0, audioCtx.currentTime);
      listener.forwardY.setValueAtTime(0, audioCtx.currentTime);
      listener.forwardZ.setValueAtTime(-1, audioCtx.currentTime);
      listener.upX.setValueAtTime(0, audioCtx.currentTime);
      listener.upY.setValueAtTime(1, audioCtx.currentTime);
      listener.upZ.setValueAtTime(0, audioCtx.currentTime);
    } else {
      listener.setOrientation(0,0,-1,0,1,0);
    }

    var source;

    var play = document.querySelector('.play');
    var stop = document.querySelector('.stop');

    var boomBox = document.querySelector('.boom-box');

    var listenerData = document.querySelector('.listener-data');
    var pannerData = document.querySelector('.panner-data');

    leftBound = (-xPos) + 50;
    rightBound = xPos - 50;

    xIterator = WIDTH/150;

    // listener will always be in the same place for this demo

    if(listener.positionX) {
      listener.positionX.setValueAtTime(xPos, audioCtx.currentTime);
      listener.positionY.setValueAtTime(yPos, audioCtx.currentTime);
      listener.positionZ.setValueAtTime(300, audioCtx.currentTime);
    } else {
      listener.setPosition(xPos,yPos,300);
    }

    listenerData.textContent = `Listener data: X ${xPos} Y ${yPos} Z 300`;

    // panner will move as the boombox graphic moves around on the screen
    function positionPanner() {
      if(panner.positionX) {
        panner.positionX.setValueAtTime(xPos, audioCtx.currentTime);
        panner.positionY.setValueAtTime(yPos, audioCtx.currentTime);
        panner.positionZ.setValueAtTime(zPos, audioCtx.currentTime);
      } else {
        panner.setPosition(xPos,yPos,zPos);
      }
      pannerData.textContent = `Panner data: X ${xPos} Y ${yPos} Z ${zPos}`;
    }

**Note**

In terms of working out what position values to apply to the listener and panner, to make the sound appropriate to what the visuals are doing on screen, there is quite a bit of math involved, but you will soon get used to it with a bit of experimentation.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#pannernode">Web Audio API<br />
<span class="small">The definition of 'PannerNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`PannerNode`

14

12

25

No

15

14.1

6-14.1

≤37

18

25

14

14.5

6-14.5

1.0

`PannerNode`

55

Before Chrome 59, the default values were not supported.

79

53

No

42

14.1

55

Before version 59, the default values were not supported.

55

Before Chrome 59, the default values were not supported.

53

42

14.5

6.0

Before Samsung Internet 7.0, the default values were not supported.

`coneInnerAngle`

14

12

25

No

15

6

≤37

18

25

14

6

1.0

`coneOuterAngle`

14

12

25

No

15

6

≤37

18

25

14

6

1.0

`coneOuterGain`

14

12

25

No

15

6

≤37

18

25

14

6

1.0

`distanceModel`

14

12

25

No

15

6

≤37

18

25

14

6

1.0

`maxDistance`

14

12

25

No

15

6

≤37

18

25

14

6

1.0

`orientationX`

52

79

50

No

39

14.1

52

52

50

41

14.5

6.0

`orientationY`

52

79

50

No

39

14.1

52

52

50

41

14.5

6.0

`orientationZ`

52

79

50

No

39

14.1

52

52

50

41

14.5

6.0

`panningModel`

14

12

25

No

15

6

≤37

18

25

14

6

1.0

`positionX`

52

79

50

No

39

14.1

52

52

50

41

14.5

6.0

`positionY`

52

79

50

No

39

14.1

52

52

50

41

14.5

6.0

`positionZ`

52

79

50

No

39

14.1

52

52

50

41

14.5

6.0

`refDistance`

14

12

25

No

15

6

≤37

18

25

14

6

1.0

`rolloffFactor`

14

12

25

No

15

6

≤37

18

25

14

6

1.0

`setOrientation`

14

12

25

No

15

6

≤37

18

25

14

6

1.0

`setPosition`

14

12

25

No

15

6

≤37

18

25

14

6

1.0

`setVelocity`

14-56

12-79

25-63

No

15-43

6-14.1

≤37-56

18-56

25-63

14-43

6-14.5

1.0-6.0

See also
--------

-   [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PannerNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PannerNode</a>
