Redirections
============

*URL redirection*, also known as *URL forwarding*, is a technique to give more than one URL address to a page, a form, or a whole Web site/application. HTTP has a special kind of response, called a ***HTTP redirect***, for this operation.

Redirects accomplish numerous goals:

-   Temporary redirects during site maintenance or downtime
-   Permanent redirects to preserve existing links/bookmarks after changing the site's URLs, progress pages when uploading a file, etc.

Principle
---------

In HTTP, redirection is triggered by a server sending a special *redirect* response to a request. Redirect responses have [status codes](status) that start with `3`, and a [`Location`](headers/location) header holding the URL to redirect to.

When browsers receive a redirect, they immediately load the new URL provided in the `Location` header. Besides the small performance hit of an additional round-trip, users rarely notice the redirection.

![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAtsAAAGECAMAAADQnhwlAAAACXBIWXMAABDrAAAQ6wFQlOh8AAADAFBMVEVHcEz8/fX6+e/Kysr8//3+++nm9v3///zGxsb4//735MFheZ/kxKJkQyKke2B4ZUEAFkTFnnlQUVG/4PZUVFR3lcSeveF3d3b07eM/YXZ4nMQfPmK3t7f58N768+RnZ2fz9/bDxcjW6vZycnIAACDk9Pzo5eIkHETHyc3b7fiVk5PR4u5GHgDa4+yZmJbh7/inx+SJi4z36tanlX4JAADL2ud8fH2hoKElAADD4vcbCwDV0c3p3dDz+fn358jq6upEQ0SmpaTBr6DJ0NnUtJavr6+Zs9ay0evgwZ/d3NjD2OrY2NhZOBWOrNHQzcpUc5NkhKaKhoLr1rhXVlQuLS8QKVDn4thBYnnWyLyutsC6lHMgKTc0JxwzMjPc08qsjWyzvMmRoLEMGCN5mMUiEATLp4ZgQR4mGg4dHx8IAg3p0bIDAwMUIS4uJBe/vr6vnH+Obk+Ze1+2xdatrKkSAACEf39RbI2gweG0o405OTokLD86KyBaeJdJQTZcXFwkGQk6GAZrbWwADBs/VXUAABS0qZhQLBGQkJMcAABZU0ju2ruVd1nDt6yescFyjaUaJTOMcVl+h5B5X1Caud1fYWGKa0eXqbtnXVHaupajqbIZMlc+SFBCTllqYloyT3PQvalugZcQGyYaEgktSGtHY4glJCWYnKHy4cVUXGgTDhFLV2NWWFlHJBYZGRhXXoAOCANsirRyVDMmR2dGPDA0Q08PAhgOCh4pN0ciACCHpcxJaIqBnchsTTA3EgEgFQsPH0Z6WjpdZG5MMyNRSDpVOyZVTEI3NjUvPUsRHyxNTk0BBhiFZUEKEiEiOFZ3bWOCXjwJG0YADR8mQWJCLSIMCwvSsI/UwbUBETN9k6mghGCDnbFjWVAXABEVFBZkbHYnHxQzERWlimUZPWASGR0lMEkCECYKGCklHEaLlKAgF0I6TmY8IA6eiXCkmo9iSivly6tnOi5CX4ZDWn8wDwMiCSpxdogCDj5BHAxnb4kdChOEcnhFY3cACC0tHxAAAAAAAA31U6NCAAAA/nRSTlMABAc1AgUNATkDGoo1tnuZ61quJ6tuSIkSpmrHSA8MmAo7G438DxrdNxdrItkeZxM/dRRn/SiDX/Ql8S4gCBcWu1pNMUVQUTU5JCwnwlkykoF5J6rR2h2lNEtk2NbNKm1FYups61G54+H7Kvzh2kFhjH49VPp/mEVaxtTRjb2j5d+T9q39Vcxv96wjg0ZTeNyJeppMn49aoEBX0bq0nLU/gubsvKHbZB2l8Kuo0+af9nqmv8LA9/LL8l+dZqzk6OGgnce2v7LJxeOy+ZXuy5Ga5fTDzfRJOvBxd2ik9+qV3+RxyujQ8ercbeG12XNksjC6pajo64nw2pDvh6P23s9bwMwAACAASURBVHja7J0JVFTXGccv4wyPRUTQYVDBjMhwWEIQxIkCIwFFkSiuMW6ICBEloihCwcREoxY34g7mKCaxak9cqtattjaitkaJjceImsSYxLq0J6ehbXpMe5Lm0vuW2WBmJMArMPx/5/DmzuXOu87//vnm+9578yQEAAAAAAAAAAAAAAAAAAAAAAA6PUM1msXGLQAdmsTwqmWlGc+tmKoQnqZSmm3cAtlRvq3xLb2UsbP/LBXEaGX6bqFG7mdxrKMrpWph2xRvJ5fpIGFLmPKKSf7LAyBHqzJ5BlN16Qq9vvI91ijmjN5uGtwh2gMatoCEOEo3Pk5ZUNg/l9KaNAjSihjyKZ0vxgvt32Ip7f3TvB2zBN5uEdWUeiqFluIYpbshSCvSjYWNMOOThZQ+1EneNqSnJ4q9gSlFRdGLxVzckN5FR1wLi4r2R7JnqvRplJanx3PQsZlwT9PbCmNymFN7wmBTcW6DfvPkLunGdfLvkh5ib5gCmprCdg6l5iyP2/J4mFLydqoUvQ1bYoVkcHYF/2wdpWcWHhE6PDniIeaJ3d0hZPO9/Z2L8UmgGMCtFWfrMOYspcEs7vxWGlfAFsHeMFQ/JoZT2qdh1DXVkry3FX+g9N3++kqm42fsKXPzCXrqfP+LTNQRJOYKS9Z3+n4Lbzfb26Mp/cS6q7HiBymdWxP1e3pbKwxQCS07w+BtE+spPUocefsepb9wZY95r9OaMEFC+if+s3GgmByylGYIVGwBLKmjuypcLXpsKL4xjbhwBXw0keLRWPvDIKkRb0r9HHlbtZw+jBJ6fYS/AiZhTZAQPHJoH9HbqCVbFLivCYnF6S+yIsUOG4rXC4dP8ij9Vio/WYfdYcDC22mOvD2B0mKp0lnDB2om4Upjosin2fB2i0leJh3eXvoJn3PYUPxjTkpf/stnHH3j6J+V9ocBC28PcOTtlyj9+hmRHHpOyUvoKY6aA2+3FiHfVIkncOan2VRcqiEzhRKSj9PZjoYBie2svHbkbR9qATOz2dte8HZrErihagml57QOFPdfwgdozou+EeVoYQAxxYLiJ3j79FNG/qOEt2Uk4Uc+MNtXnByjq8LI0CV0L3G0MEBinXC2xkTeZtdGOYnVcRR4W95jJkcdKE5u8tnIPTGLdDAMSGX6zyl91fRMdYFeTWtYS+6Ft2VDOfDOPtNZYd6vng4U5w9s/5q7QF9wJ44WBhBzLDCdPHCvZsW20srbLsvpdVF8w1NZUTa9PRIiNp8PWQloPLzBHeOLH/uK8yckV6VL8drRMCAJyqpJemAY09cl+QaljyIbnLv5lNmdP0Wg8Bauo2robal2B81kAisgVw4SmqNYZLns6kBxIVhn0FXC+QVHw4DR3AV8pX219HgtfwXxyAa1JDFcoPT+F/qP3qe0j6qxt9nHaM22i5GQsbmU8BeFbOy57SB/FPCNxY4UF8/QS+cXHA0DJt6+aPxqwjvCud9Uq2ultNJXF+p/5WqV1s2h3zFvK27wv0PK3Xzi78RSo8JijLCnuFhtSifeHQ4DZhIL9RpNdKh0QVpgP7cQ45YnZrVeo3/LX4wW/dwipDVxC+UTRVVJUfRUXFjZErQbxms0+r/205p6bCsuPunn8uRhoJVyGkgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAADQvgmABMBJoZAAwNsAdCj8IQFwUsZDAjk4DAmQk0BWIBf7IIEcREMC4KTgXn/tgCuQADkJFgFA1g7FQUggB/0gAXBSCiFB23MXEiAnwSIAyNqhCIcEcoD7a7cDnocEcqCBBPjwhKwAi9ChyIAEbU86JABOShIkQNxGTgIga4diHiSQAxwnAQDIxgpIIAe1kACJIWQFclEKCeTgWUgAnJRQSND2TIIEyEmwCACydiiKIIEcjIIEwEkpgwRtz8uQADkJFgE0HdwPsB2A6wCBs7IAEsjBa5AAOQlkBViEDsVzkKDtSYQEwEnBjaJlYS4kaBvCyyKRkyDVc0pW0JczohMQYAgXr5Na684bTFuGqioNH4cd1NsMs707L4Y1W6VWwmNFcha/lbw92K+p+1BWalHGtDNvS/bu1AU9s7AyICopPJL4z5p8dmWo/ywlmfLM/kTJ28qAUWU6bkP4W8zxIeFJCVkuU1gyx36kvoT9+wdxN+elRCEnaXfe5u1Nozq3tw1rDh+4cT0qNbjwy+meqcG6T2u23XgYJHrbsOa9SxHXrq/If6AdmvOgkgbr5qgJmaPmxL4d9QfW0hHV9b4jbXgbtDFzNW6+nTxuqwaPIzFLftY1WOftSdh2YAUxxI0Rva0aPJbk1Q8ggXFjMm+7kvXBOi/mbS+11LfoBQVZvXhosKuNPeN0b5vGbWbszi6E4G0//sHk7fjK0owjaqO3/chwutPXN3ZcQR9Chhu9LfX9Pe7+tnLOI1hnY8+4TKftvD1XI32j7zC8belt/3+tjJ882MLbO1aVBwQEDOK9fZN5O5two9VSHwksqYwdZ9vbLci3A11lf9//hynaivGaUBQ9jb1dzLydELuV3KTZZm+vix1BFN9HZN6OItdYvj2WeMSppb6FFYRU/+BRH9aq3ua8fmdqKpWyvG3TFC4GW7/u6yzL26m/IGJYs5U/DMh+WBW5/epKtj00f+3G/KWhwsFB/nfc9lWvzZifOPT96Rdrg3Wb6g/u23NU6htYv2tt7JmY2NMjbOzZ7JSSos3DAoPI811ERhHiHyo2QxU2/k15t02fA3X0xaa8C21ol1B3VSi/u3jzJOYmly40FA2mUCRX7VE32lnC+OPd3Z1keTv1F/s4tyilm4496ALdlNrCWWzrWpjiGhIQ5cavvlLYTnl2qpaQxKQU5nxuQ1LEzCBj36ikpAjWLgxqvGe9sZEct0v/Ue5dT67gldm+jOO9CPFhrden+/ru6WHj31Q9ztRU+vRqyrvImzG7Z1iM75ene3BPn/BdVn+Fn8SiqZqYzyY7PrvceopFH2ze0rtRtrLvfOE5Z/E2DsQ2ma42M2vHsk74fAwfIr08maOFINy1l9jyzmZVqQ1v//KURYrTNG9Le/b2Y4YeQoZ2V/KTWDQJ6cZ7ePjJIQ2n6NbbVqL2F3i705G3S9vkscbbvlS/KjzcKheNypGuP4gtb7Vtb28vluL9HyedqBC8rRx4fNLOCrF39cVJpe980/B6APFPQPB2D+LBUgrB26am0cMf9raewum9jRsgyYny35GW0dX9K1eOlYepb4re3tQ4mYn5PEJ4zHyUNTk5/xIzpss/HswKKflxLMf+MtZvLE+8VUfVduP2ljDB0HlvWjYlD3N1Z6ymcH5v48Z1siDdZtHwG3Ma43N52x1zVuOttvm6Rf8UHjxODWJb/1zm7cwHfF0ak+vH8plHfDLBzclu6O3LrzHyxUtgPMyloKnZjb3Cv+BylOUUyElAi2QVvH1Lo9FrIojPxwuSTz7B231zxPP308S0IZN5u060bOZYZkWxzJzZ8EIstmdGnQNv1x6+O+9ApNUU8DZoHtJtzV2+YpF2ZnTZnQ+C+KxY+b2CS3Fx4O17u6XwLabp01jePFqsAKftNSfMxF6+bdfbaoPBvcEUncDbQE64OvEsiY+n0YHcIZ19b6uWDxAbL4kGLGAvOSvuoYDtoVtxc73du/EU1v0uOs75vN0fBpQD438jlPpwgMnbL1p5O9uWSftIJyL75vJ1X2ote8mOR3zqPfwkKwATTvI74zK/tldL8vAH/iRMTQtvm6aw6nc/RHebva10kkVATiKvrCVHDpRFVx35jNt0492JPXv2nHiKeVt152Du/9g7E6AorjSOfwwztjAQZECZhGOBEYKDgOFwdLgE8QIBNWi4FDSKeCEqGk88ABNBxSgiGA2eeGZNiHGr1DUxYlw13lGje5jyirsazW7WVLKpNPtedw8MM0B5tQPD96uamVc97/Xxf/9+/XX3N9NzHecbNrLaW3+Hs0q7W73xwLLNe7pBxpJ/+K9bwt14mZ131N9pXppBTm3QPFJNuefGiesARY7H6hwduQr1Rdme9LmOjv0NFzHV8U06nft1hqwXO5xztOubjssmODr+0SzsjQ9CFAX/+pLyByene94k6u4oQI74TAIthBg2Gje8IRpQqlUzPZVc7bCZTm8Id1sihjr1zDT0XVjHjj5WMjJDcrIYSWfswaVC1RcZS1qKNFzECH51+Isn0U7TuU+pDzexL/Yg0hzP9LjloP6ir9dLWASO2+0lJkGwE1BW5EWDD7AVhTiUwPQwKIEYqFECPHiirAh2Qpvi7yiB6ZmBEiBmSkeUQAz2oAQYk6CsCHZCm+IkSmB6/FACxEzBP4oWhe0oAcYkKCsiFvgAW1EYihIgZooSJcATeoxJEOwElBV5OvAGmii4oASImYJpOq0AfIAtxiTYCQjK2rbA+5KigD9nagV4owRigPdu8OCJsiLYCW0LzJVqBXigBIiZgg+wFYUFKAHGJCgrIhYTUAIx+ANKgCCIWPRECcTgG5QAA0OUFRGLJJRADPCxnYi5MgolMD1foQQYk2AnIChrmwKfLykKoSgBYqb4owSmZxJKgDEJdgLy5OxCCUwP5gEi5oolSiAG+SgBxiQoK4Kd0KbogxKYnkEoAWKmvIsSiEE6SoAxCcqKiAU+wFYUZqIEiJnijhKYHkeUAGMS7AQEZW1TKAwnWCSEEiQvfEHFR9vTcRqfm9AasWZvZWfvG9PlRc/XpqtXO1KxHxrJ9Gw39nZvALes9VIYpa4OAFBG+U9ngFmu1riDMpOhr+RBP8RCsroyHIQ6hGTfaLVvoEZDBvxQtb83JMeSQ4BLJGlXSSZ5q6Oq2pW3MSZpjZ1gzTqQ95JOVlPZnbVfhyjHntionc98cmHxlFKvgZ2sgLyydqXFT63beWOuhK9Dm2Xt2jDv7vYy7UEIYnceWzLgNNk5Kgp7nyPtbrtHjL29jkVvIy+XocbeLs/J8R+7TfbnIcDUzhrI+sKV0RPZd0CpPWRDvE1etmcs6Lc7+vTl69Bmth8yxewhmOYs+0kOzOBtNnUOcK5mWF0PcNXGZ1x1h5J25W2985XQnk5oM5MQaezttJHj2UR317y5CsXCGrf0U4p77peJMZnBcp235eCa15/UFepw3pZz0Yy9s2seCdVXXZR2HxKuPRTDfqBQBA/JXQ9Q0a68PbTe2NtZFq+ztpqYpDcEjk0Et/c2ubi4eIBk+dktNXrejuG87fbeGlJXV0fnbYcGb8O09ePueFUUriAVQnJvAsS0v5iEMzaL3m5d8bZ9XQ+LRYkAQZlVmxhI7TSMXQPWefED67pBLudt+u2OI9P5Oo28bbFoPlgtPQhhE+Ztg+Lg/iD5n2/G1QA43dXLu2+7kTW73tjobZOR06S3mdrSDrODNywo7DEx70T+loPM6SVHx59xD9SmHfvoqiRLDjCb3bDwtoSvw51LCt6+Sb7ZfeluCBnmSYzOrC3MT58cGXEk7diErl4lP1u0F1k7lE1i6/mGRUyBUa6UzMOdhuEeHWBEVCWJxpUzonwYYK5oUqwAvKNSlB2lo/xIjThNCjlh4usQyDTaMpIMzYM0lTT8CPOwotcGNSlkfoGafpEe0nY0bvcB73fnTMJxGy9Wmams3mre3uht04D/TyIKZcInZ2/0NmKeeKtfxoNUGXwIrhFG/wdokUBVUsY1UVe2MbaZuTxYgUo24qU/N8HmvJQvuDX1rUV4U1OlcR6+uvIgj24tV37afU0qfemik2VKW4y3rdnhZNvsbzbl7V5NZlA9GABBKS0tM3o0nsY8JXGWln4QZmnpC0ofSw4fiX4xkiv4NTQ4/DF9Dxv6aScrw3lJojdu6dzEMqrSSxVHCjgjM2vHnMxb2XzlMEvuMgCToL/IFnnIvmUwxWiVXxDK+p3SjmUbbX26sbf3DSHedhbyoK74QrhLN3B1seK9HR6lTmFAyJRK9q+OhFH3V/om+wrZVK6ZkZpq7iaNa2ZytVQSpc5kvA8X+OhlWSX7LVdPBxCyqMKqq0PM0NvP+1+XJcH7r0PQsSWbwH6MQrEwTaHY4qBfLDpep1AQZ+ruhw37mqasuW4/OuNzI29PO/H+6teaGOUGj2bArVZOy6mTu0Hx2AHNVr6mretNPh6xm799wg2Q2r9qMMVwlV8Ur8gbNin8dauWqloXPiiMpd7m86AOz4IKdgiknpdx3nZNLz2rLWD4TKlrp8ou3fEM2re/PEuuy6Y6lV220JmYHwae2vUvt/TSxdrEmBtpcr0sq6zsE8fZLgyfRVVRt3sZ29/8vJ3wvIfX7tRLEWSEsSfjn93bALYO+kWQfU8Ov24/bhPqn5uvO7Z+31TvvvJacwsauJUubWk83Z+2NV/Z9jjNGjqneOuJt8DI24arLIK3DbZ+jvG47VB7UWrvLORKpQ6XrsreCl8c5GOSjAsBEFMXwmVKxQaVQ7g2nuneBWzlumwq8nG5awcaABLLpt4NgIpCTzs5NGRZgW2NlFkqn8hnUU0bLoGi6RiTGHubZmNaO/MesevMe7uhKPSi9Xm+L60/83xGb0+jHRv+XzqYDhsubd7bHuTAEHFgOTWsNOjTpA/KSSuVSrVJyr+TCGdZ0shf+Hzn6ONJ+8ub8nb9KjdULlKpAgLP9nksSVa9sTpJPur4yHIaLp1dkLSB2oKZphq0ceScb7k1q2+VrCov6pO0hx7wd6i+vE3W4LGk0dYHqVSkNcu9N/Z2cd4hmhfC5UHtmOA5ePSdDovieW/nErXd8lZwmVIQum7OyH2deW/rMk6Ir/lfIdD3VYUKxQK2h5635dzdefISsqgeaW+VrWDQ282P2wNX8oZe5alfFHrxkWDH3IPwLN6+4r9uM11OILeLBAo7SpPedvjkY7If2BDDWvx4O9N79u+JjIXm0u5K8l67tZKBjDH3/BL+OpmG0xl3R4+InvJVM96mq6xX+YrmfvWR33K+PBS2ii0IncKurPq1GzCr3/fxC/obvUFedJ+dFVeVTkOhhlak7uQVYSV/IWNoYPXDrRqNptKq0dZHa38hxl/88EyIobfh2p0MZyEPitl7/bOA7pWFAby3V/He5jKlLH4qCB3RS/B2jM7bXnreLplMZuESIHg7Rt/bQhYVuM5eFzzE/Lxt+dze3pCfn7/MWThJaji70xVlJLKUVv3Onf+B668Oz+Tt6MXj/0Q71po7BZO93pK3bT53/y6WejvjNj39DBzfBWCcM9m1ZItInF58gHNR7n/IzLiicryxt3WrrFeZzvoUf5HN5owVlCQCZOm2hYZf5GvqjoqaRosAG+pwprZHfUzCGGx9yb/p4ei7AUYxCUj25jkLuVKwNns9Y5ddI1wnSb3gCePqfLlMqZTgNXCZfZvpHk+8WsxnUzX2Nq0d9lhiNwsasqwEbwtZVFPJEeiL38zP29XP7e3rOTk5RS14u9etj/aVXuf79FoBPJO3yfh0biuZRQTnbbd/tuRtZvDJGoZ6+yF/sSwjUbC1/UUyh9Qz/ShTf7aA1Fn898be1q2yXmU663eEq5iv8oumEVfEzPwy1TxuPWx7C8GZfisbLu6369JsvK38lTSb8CFj7G34P3tXAhTFlYbfsD30jKALOHEmBTNyCMWhnEmQgVFRVHBRICKriIoJiAfe4IEYD4wrQkTjWeJNVKImLsZ4rLfxynpkDeom6nrtlmXUJLWxdq1UpZp9x8x0Dw6GEibDzP5f1VDdr9/R/O/r1997/f73koUHyDgP6rpQirIFOsJkWLJSN6dwY1Eamyll2FNYXjWxpM/iqmW4L8lmUyVjRidTbpO/vvVbVx2v4VZfKushzrJiP+MsqpiGDeVvHAZN0rTeborb3/kaTOPQhnn9X5XbSP7Mn+htktXOl+ltrPZxBwrzj0+NoyHZpE94/yfEnyZyddTwzgy+aCrr1ma/yG3TLUsis6wbc3tzUW1fn9A5r5kvE0NIU7m//ivcJh1juRDZ+A78iCwf1Mc0D8rgF4S0flT3c4pAJO8bG4yMM6Vcp/d1DfKJyJo+IL6bcTaVqx+HdH7ERuQIKSsTp3HId3ouL86yMv3YLKqUxMQwJxwDvGZzbks4nL2Pt8ZtnW8zuK28h7mtfE5YkF2DXsZtZYqScuroESbx3agYCnM/IccH19ebv5rkb2LXm9DblpGtc7v9EfFfNXNbmurXua35OSz7oBN25JwAYl9SVJ4Wh3RAzXj4pFOjgTbGMWFR/5dxe+gjzAP+2/VEGHSowU3SxMMv4TZrrIkWWPeQ6N6kz2mTtLr0JH2ly/ekEyJpi12QroDkk3ztj1bHABtFFrOmeVNux/Gp5FFLynvXfJkYQppKqklGkX40Hy9rZJWKXc+XAY9sgc4tS64ZXFR9E8Wcvbo7Aslv7S4oUdEXvXj4fvm4wapPWUXmXzZVqHawqnycyhjeQRAYWSerBueUqFQrG5WRUF+lzviikE6j0OXsz5izSdlUZP7DvOrdvjj7zy7gRnLUwjvhaxeyDuDSjw+wcb+sOQejojbqf8IU26zfFbrxQPnW3SGW327EWxYj695773g1veOkuVvd0NSSNWhMdf/J76yIOvswp+RTTrP7eHU/9PbZqziGmCpm7lZ8PvXuQULupfpT4QH1hSGot4r+9yr2RGv0X8Mc17aot2UKhaIbSlAogjnED8InCjpGIB4GkYM+9J3L0Q8vFFywgoYzohevYII8iwYqIl54NwzNUI826hbfcPVorunI8fROlPgCeRQSitVRRt7yg0xTjJTvq9WPmLzUhAYU+2sUCkvlL7llMbJ4xxryj2Up/NFIP1d0Q60e7ZqAg4khemKVS/8nc6oEmtFIBZPKPTLUK6bJaQ4Efq7s5fB8JnDbJuj12xWlq5WDvV+EpzcHG9gCnA+DfHyepPWBDWxtgu1gAnvi6SqMm6BJ2qLeBrQGYANbm+AtMAHASSEDE9gfsIEtaBIztK5QCYA2a9aEFswY5tm3bgJO6QSV8CXw0BZo4dryfDxxiwxpZuyREjp7erw6K8f/3eTv5S4IcVCJAKto4Z4gslte+oNea5oX2eWQxAUxqezV/ctPppsPua4dHb8SxgIP26Ymad/sXVnkh1pHJu88IL4oeGfgNujtNs/tlLWZI+4w2kVfGZG5axhxsDJ7FKKYK+PuBAQE0FU0ZjHfRYtUEudCRPwTm3xmVjOnAs3yc5mngii3TZ6RFiWLkOasqziXuYHMn+odEEBSxDT2VbQDooCHtoBr63E76faWlJEfPiRzkpYWpKVkxeRhSS16FKLKmHGPYmNj6ZylzbHfG9dwEFNJnAuxfukuDGlCtETfpjOdNBPL+qSsLjzeUeIZKS1Z0imQui1OfByc9X0BFjVD62cQUlf+8PhNx68EgBVktBq3DQV0mt+33hziqe8gWmdmGJvMbZDqbQObnS9JZeFcqDwt/LuJAqeyCxfpGgv3ifeV6Bn5QsnGLqc555N/If3ZnXn4WZqajt5eFYjqBoImAU3yEm7zEcj9AR0FcbkXguR0qQUkIxtVSDwK5VJuGz1PJKksJvIjrqkF0XR06R3mh0NczTpKPSOlJUu5bcqZm/8NdWYc8xp+AGpQhXCYe+4P3HZObG8dbhu+UyYx/xXuWBjq8Tdzsyn1KLTGbUkqCwespnGfuYIZbjP3wWMdpZ6RkpItuG3KWf6slvkyYsWt/a/hefGm6BP2HyGHDWzbKCi3MVPHn6CeV9GHXDGJzW2h1KPQGrclqSy5LQu0/m1HPj+SiejFtPmOXtJR6hkpKdkqt/nF4tpg/OK+Q7Q/zyqzvwlhA1ub4MtW4zZ3Jg1rZgNdauyrTYSxWfWRFh6FsntkERttmJHbtKsoTSXVJMo9wiarxXl6G7uYo/6FG2750XFxFp6R5pKtaxKUX0iL701Gay5ud0N1d//sDMIQ0PpmVa7drT+vUqnKcectqP5gVMbEGtLp154eviJq7bhSDokehTh4dVVUxi39MkxD4jE4mHoMiqksnAvlTYyTKPeYGl7u6IXijDmP86pvSj0jxZIlkOTMP8VR1ae3krVGsoUBKP+F9ROA286CFk5BY46RRv9C2Sy1OpcpCb63Wv0nOtRt9ig0ho4mosHkMUg0ijmVpXNhb7XVYef8IWZ5zN9QB3zAxyuoY6LZM1IsWYRFzgkZ6reGUSGk9eOQwc9g/0qAyZgA0gQ74Vq6MIneNgCXD8cXhgAwa5tFJpjAFgh1WvHSy4x+UM3/l3DapTGi/2BGm5+u0Qt4CJoEKgEAZnUodAYTgCYBAJqPWDCB/XENTACaBCoB0HzsBRPYHzvABAAnxe/ABLbAAjABaBIwKwAqwaEwG0xgf6SACQBOCtg3wSbIAROAJgGzAmwF+HZjExSDCQAAgK2wCkxgC0wAE4AwBLMCbIVeYAJbYDqYAOCkmAQmsD9gA1vQJFAJADCrYyEDTGAL9AQT2B8uYAJoMuDlCQCzQiXYFLJB8Rgted8sPeXb7LhPP2jiQu8t0EVvm9CYDhxvbfl2wj/Hjt37TjO2X3zanyVIs0iehty7BDa7tPZuVok9GlV+Ayxqm5g9IorN3PZxQG7HIaQbs55DI0N3RCBkiN0RFhuiyeUR+bEwTWL4NH7kk2VkDWnD1CG5SkNi6DC6hDU5S+6SErsD0zs6PHQAy3Not8rQabjzkRiay/fM5VC8Hw4LM3KbrwyNxQ19UPiOEIQSSJqgo2XBKcEIxYeGByHOJyIxtFujm/QCitkN5wRBoPQWHJDbZFfFCg/lZKH2zKU3udMXFuiFTskeSpRsCtPknd+oL43Zu5/s4qk5fam2Z07VFX0ZbzzbLBxYNc+bH6/fv7aB7RQ3Zuz5s0InXU7VAn3a+AZ//swvvtz8dxm3+bqrCyZWBf6or/5sYVzyGxvKhX5Jd4e7dXiAYoTaLxb2Nyz5ZFf91QjQ222J2xiZUY7I7TWTJoXnfSQ/lo74MzN+FPqjJKGTO+a2u4cLC0sWwtCN0XxX5mdcewAAER1JREFUpls8vdEozL2khjjjmXtDJLrexbWuhkMVbIeM9vs4frFb9sMItG5Rt2MDtR8fj0xoMLbb44WZSKM/UlfDK8vXVG7hUfsZ6PduqIO3/Blu01M/kndPR9FFMy1vUgUUsze3Kb1THI3bw0cUCGm+2qISL695+zBJkW6JkdsaFqbL+avXI18Jt6d4YxnD+Ee4jZNgzZ1a6OWV84uvSVW3d1u+yMtrrhD51YzrDy6mZ69nrHe7jtU5n+qWWkpOe16ZfW7b64zb2iKc//Kv5d07IfJrhBQBYG9MmBvu4mDcjkPReWmY0Ft8fHz8CPUwywi3kzy0LAy5VF7Ztk8pcnt5I24HEn6nluG4w5QitysKcYBPRP76KWmeNSdLjX3JJCO3aaeybvi0rB+awe1/QPNp73Z7wlzB4b6gUb3t2RApm5+GUEzueCESeWK93RCCpni4sLDNWDlke8i6MjHtOYTPvuqP8hv8jWeM24EnL8vIgIfIbRIr4T8u0Z9/srLdgW2RxitLhZWoXdHAussyZf2yxaVo5//YOxOgKK48jL8Ze3gzgCDD6AzhyCCBGiAoIMcKIgyggngCohOQVYOiKCiHBgGPiIIb8Q5R4hHQbDzQGK/EECTxxKx4JComHtEY102ZaO1WUru12a1mX3fPBYymLO2dg/+vqoc3Pa97mq+/ef29np5+OROR8wLibcHSCiSpajLpbcjb5vX27LgBsVb4o1XW2/j0WrvSsK2LlgdTJ9tu7qH7hUZlntp/XcjNyytpXbyjCVetXcMsML0jLrx8zrYS7lQgebaCeDvpFd/UlrK0sDVcX9KBmZRXGt5u2UnhUcsHUku5sELm4vPLTuReUObl3C9vG3x+WePtw9NW17ZVFt5DpfTeKw/CY1ZuRMzUiern+hexn0Up7mlnXd5mjW2ViLwZ18V626EMdR35H4TFxRmk2fRTaxRiSjtPUaxWYZRRzJ7iwzUapWhYpErrmxpNrDeFvMjkqVaHczOzg9hJUqMuIik7hSwbncC9Eh2EcHskk1wU6joFouKLg5QegcriKRmkQnJknS+ixCSziLucMX++PozjZf04jpT5h47G3CDECAlMjqvnZWkG8dAZO84WjkImunJmplMm8Sqdvz7Bsz9K6cVBjK9QcUWVyb5O80d6l9P04Be8aUpVL5VEpGLeOtqwQYYiHsMWDBuWd5354Arjt+3o221lQ8Yf7iOxVFvYRDAUnRlhwbLGR22NuJh72wHPK58mJRx2I6mflJZkSqU7XE0snNpmOFtOver6gjctL2uazD9UeucTV/zqEemiji+ZDTIqitLyyYaR4KVb4ItxzGNh6/oNL3VLK38+Ufy5xXp7MQJ4wOgWoqm3mC6tkOmuurDjnzu6cSXn10lX1ZRzL1UYBYIX7m3tVjj3I+sejIb2oZgNMioi5MR4OPGo9oCx62PdcMBOL5lqV/4mgd3do1AbitqTie2kHXQhzsHI8T9cybmvaW/bH2VP6KCB686mn/BjvZ28KX3yd5zFQi9OTt+r6XQxCy70Sd42eeE3bEhXrjqbvpW8l5ePjw9p/nf5+NR3GcCdeW+tt12RPfO9gJtxUefh81on1y5AVuptGMCW50xC/SvIuMWU3LXDxGtJazhvr+vffdl5TewfRX5lQnLtnBbi7cRb9cnZGx4wPeO3cscmZwzK6RRy8Yqf6AUp72Uxhg/Nf6jKeJQ7DgkLH3xAOt2hg46+g5/Ubm/wZw2dt8a4qPUwfvwp91m6FWit3oYTsbxguD9JzDHDKRSXc2/fNFyD6NzX5KKe/+ba8vPvM4/f064oJpc9Uf+tO4Vwbzb8bu7SgWPnbj7EHCWaGCfvyhmJlL8q0c9TUeoEqmsmObeYkM91v+0Na9IXnUhYUsw7x4X+wn8ga/U23OuSZ1hvt8vlEfJA5PJ1QfzR3/P2t5XsH8ldtkkX/eKKHO+xLa/wrj8S/couLvDuvExvJhvbu5OjxNJvhjHM6IvwqBGeKydIXJq65e2vCwiPn+Ltq/tvz9rLHW68ckZYq7dj4Yd9vOCjLwmII1F2SPXN1v5M0qV+E+Jhgqd4O2YJZ6aYW2y7SR13RYkTuXRzPBANvWzSSWxsZ7wt+mX3yywkcc/7yOVh1Yjaz7p5W5e3n+jtvjExurnfb0fW6u35EeBDfqMefsyZy8VB5yq8z/cp3n7tEBePcRXr8dCVrijvc/Zkc+gxOyQ61v+p3sZVhlHWp7sd/LSwYtTIZ/e2wcOipcGmvC3wxZbv7Qi44SgvnDUUk/4arPf2xE7eft1UM/iT7muoP94nDbeoedZgRJ0eSzJzzN+ZAH5pO+PzjCvB3TPJUHfG0HPYrl+8hnj1h9u+qbcbun07pO9LMjAn/rToi0bednGnTHhbso/ebvA2BZmkx1J6YG91yLYDN/C6Kw1pMpks7WPibdHNxtwyWUW3ytMv6KxCNZ+bP778Yc6WG8jvyich4/N3Mpd1eJ7MXB+yaVaFsaEUjS1bhqPUM199SDqbPy/7boD8ZMMbTIapJO34zq7vMKi8odFf0Xin9QZCK2SnOmQy9gChL4oas8pksuFaE+sPA3Nlacx89roZ0R9orofqmSb70yyZ7EOLtHcAWI8X0o2fKB7J5T/6kdQt1kKO4ngMUwjvuhxVNdqQZtrlPqtxtJg0xIJSuXyKNqvEy+XV/p0WEpA1xSIvbzF7DcyQ8fIIDdtYRzNXyaR0fYshYrFKIiKLkFdjmY3wZi+F0hdxLzG7PvaTNkEfODK4TedOnsTLi7jNVbEzEyw8FwKWoKvXbpEl/RuDhlvxPoDxa3nqx4AEgI0iAAnMzssggXVmPc84PQ8p0Bvytg3pilP0BIHcJlkEEvCCGiQAbBRvkMDswD0ZIevBPgBAV+sC7oHOD34ggdmxAwl4IQQkgGMn6ArAPrAqZoIEZgfGrwVsFQ+QgBe+BAkgk4CuAOwDaLeBZ0IBEgA2Cnx3ww/7QQLIJKArwBNwrRQ/wPeSgK0CvxcwP3EgAWQS2AcA6GpVwG+B+QF+dwPYKpEggdmB8Wshk8A+AJ4FuF+X+YF7XQK2SgpIwAtykAAyCegKwD6wKiaDBGZnDEgA2CgwBB+025BJANDVurgKEvACnCcBAIAv3gQJeGE2SAC5EHQFeGIhSMALcL8uwFZRgQRmJx0kgEwC+wAAXa2K+SABLySDBGZHCBLwQjVIAMdO0BWAfWBVwP0Azc8wkACwUQpAAl6QggSQSUBXAPaBVSEDCcxOLEgA2Chwn2h+gPElIZOArsD/r30RjIkm8Pp9ZXx9jzoe+lVHg9EsAnv6h5kzD0zr91zmnfrUl53ce04/xq964WwaRqg1B3EmvD0YIa8Z71IoO+CDgQgp1AOKMMI1AZFKpJiCmWlS8qORaFJAXQzS1mEZkhCvQaEDAkYiv+ZKVXICQmRiqk4KqgkoQswq6sjhYFKApgd4mzYYmwDetoxcaE+7ksdVfSRz6d2n28IVOa3boirwwa/ezF/rm9RHgsg0Y0/m6Lkdu++UCbk63IKFexrq86KObOoYnXgn08HJjbTPboipOmNm6xm6H75EVnFfeY3eu4juEd7WGRu8bSYWm/D2OwUFA3LeFx0fh/DpBUl0IGqfmke/gRRRnzkSb5Op9wUB8+quuASujjZpLOuPDu6k0KoJlLMD0nqbVEW9D1G4yiGvIxh5Ro1ufojwKNv3dkEvvbHB2xaUtzMn59JjlZ4lZVLpkkNeWX+R/qi89oovsaSDztsOyLNkOKmrraNP0XjUHKk0679KI287IO2USG+RSsPGVVWQg4Lte1uNMgzNNr2HBsxBiIm8HZozFnmtrPfw8PBGwpqLOw4ZeTuR9bbXyo2krq6OwduV5LlGovX2OmNvb16+mryWUkWerOsheVtvb2i3LShvu3QEC5aORWjQlPfqMXqtTyq9EdmXjE7q8EfzWG8zr+5qKeLqGM5+fEEiSPxU5LwAOb2LBVXG3n4rbDgS/hbYvBOL9rkjvwTb1lV3fxLO3uBtc1Bt2tv49Fq70rCti5YH55W0Lt7RhM8vO5F7QRkalXlq/3XhDGLWUnrrkvtCro62L3kPodSWsrSwNai2rfIavaV8/3bEVOUmXLt8cdac2Gv0kfKr99Cqfwp6isTE3uBtc9D9d30ibyV5jPW2QxnquliEFMVqFUa4PVIjIX1/tUYhprKZUW9TIjVCpK3D7UOmKfZUq8MRUhZPwdGR4oxwxFTVTZMiNWTV2ZFFZL6tt9sRYC0LzCQA6Ar7AHgycN+XTmA/M7ypGHQH+MfxMsUV/tfe/cc2UcZxHH/YWtsusXNdCVPTpp0RBnWwULI4skJkCUNwxLWZErZI+DGXGVxdBDXTDANuZpJM0SwmTFF+GJYs4K9ihBANMcQgqNsfizrxD2OAEEwwUWP4w+o9z11t19YpNRfkeL/+uD29Xp97ev3s9r1ru/Pnu3dGJN9cn7PBZTQD6ea9wbn/dqVcv9Yc1v4/i6uKi6tFfXFxSFRUFStVRZnNpapRnX7A8XfktL75/Vtc2X0VLXt938w8e/ruzuG2Vv0t78sdibZW1ZtjaMOpLYO5S1fM27peHib6tTE0OOTURk1CrVeInYsSkyL8yfY3RdkGj2dbq8ezrzyz2XfyD4/H89GOO43lo2fkh458b514/OOcbHd/uuvl23JXEdfC7Phxjgxs0aVBLdR75Ny1m+eKFzY1Zi88sXikdmBvjRCPeBYlRiLRtuRwgOvXmsXa/9fccVedNl1yuxBlDwpRulGIm8szm8J+Qdtv+n86YCz/5TNGw37Blac7d55sH5cfRHX0yxhPtGgP8l0JydtN8jfrQHbFc0S+SR4/V2mMbE3H1yQQhWZbfp6uRGb7Vi3QM/Vsp5tGhkvG9CSXHKm86myr+tymsu2+X7bf1WId+UX+JYi22KaO5mFV8YjTT+gjmzjbpG7fwQtlis4bZL+9YlAP9EuVmU0jw5eNED52TFx1tpV1LfI7MkMbZXtIW2ih+mVZODa1E/85vfaJagWPlu34mSdvhLqQetusbL/W29s7YHwsqDR9KJhq2ue4hO2N3/WjPt+V8sKyHT9fl+7UrSW8RB2Kys4zlex26J1/eJM2sliy1XhfkOsgmuMei2d7squrq2+abN/9w6G3X5zUM/fNDlFQtsPnV+qdqv32Tm2hJSrb/ovTZbs1tG57IwE00WqLZztVb/9dti8GIqmT1pFtjQVl+/u9K427VTldelTW27LTg1n1tu+rgPpZPyZrEu1B4d0u9tvUJGZlOyPDa99z5Mu2PzBtth3dm+uMZpnswPVsjTb5rUZ2uD9r0fv0xw8dM0bm6l9OvU22/+uxZLpmmNJU5wCN5qWMr5Wn57cnn2ucJtu20z3y3MoyOfFv0hIdlicChXu/TfgfPZq18IpxGfn2D0KpkZWp9HP9WnOssvKTq4htGZ4U4ZPjowuE/dvRjh6vOn+dbvYNdMa8h/UYt3+eirMv5h3o9Brz3cmkHtG4N9bW4/W+MnUVB5MJr9cbW6xmx8d//eKzGrWzb0s0P70np6556uyJ+a+OazvrqDaykYiI/OxZTgbNMs/KT26G0+msFvVOZ5VNOFZrN5zqvfF0c7ZsNKhSxNbf9Ne+uMqp5utB37pLL8gfUDOdC6auwh5Uc4P62b01tbUhfX5g/qz1ttwRzW6e9bzswR/U1/uQcyk1CTWJyfwjdl4Da/mOTXDNcf1aWBXf5DPHKJuAupDtCl6D68opNsE1V80mgEVx3QRzcH1JahK2K9i/XF+a2QSwqAo2AahJALIN/A8E2QQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAADAP/kTk236G+25xq4AAAAASUVORK5CYII=)

There are several types of redirects, sorted into three categories:

1.  [Permanent redirections](#Permanent_redirections)
2.  [Temporary redirections](#Temporary_redirections)
3.  [Special redirections](#Special_redirections)

### Permanent redirections

These redirections are meant to last forever. They imply that the original URL should no longer be used, and replaced with the new one.Search engine robots, RSS readers, and other crawlers will update the original URL for the resource.

<table><thead><tr class="header"><th>Code</th><th>Text</th><th>Method handling</th><th>Typical use case</th></tr></thead><tbody><tr class="odd"><td><code>301</code></td><td><code>Moved Permanently</code></td><td><a href="methods/get"><code>GET</code></a> methods unchanged.<br />
Others may or may not be changed to <a href="methods/get"><code>GET</code></a>.<sup><a href="#attr1">[1]</a></sup></td><td>Reorganization of a Web site.</td></tr><tr class="even"><td><code>308</code></td><td><code>Permanent Redirect</code></td><td>Method and body not changed.</td><td>Reorganization of a Web site, with non-GET links/operations.</td></tr></tbody></table>

\[1\] The specification did not intend to allow method changes, but there are existing user agents that do change their method. [`308`](status/308) was created to remove the ambiguity of the behavior when using non-`GET` methods.

### Temporary redirections

Sometimes the requested resource can't be accessed from its canonical location, but it can be accessed from another place. In this case, a temporary redirect can be used.

Search engine robots and other crawlers don't memorize the new, temporary URL. Temporary redirections are also used when creating, updating, or deleting resources, to show temporary progress pages.

<table><thead><tr class="header"><th>Code</th><th>Text</th><th>Method handling</th><th>Typical use case</th></tr></thead><tbody><tr class="odd"><td><code>302</code></td><td><code>Found</code></td><td><a href="methods/get"><code>GET</code></a> methods unchanged.<br />
Others may or may not be changed to <a href="methods/get"><code>GET</code></a>.<sup><a href="#attr2">[2]</a></sup></td><td>The Web page is temporarily unavailable for unforeseen reasons.</td></tr><tr class="even"><td><code>303</code></td><td><code>See Other</code></td><td><a href="methods/get"><code>GET</code></a> methods unchanged.<br />
Others <em>changed</em> to <code>GET</code> (body lost).</td><td>Used to redirect after a <a href="methods/put"><code>PUT</code></a> or a <a href="methods/post"><code>POST</code></a>, so that refreshing the result page doesn't re-trigger the operation.</td></tr><tr class="odd"><td><code>307</code></td><td><code>Temporary Redirect</code></td><td>Method and body not changed</td><td>The Web page is temporarily unavailable for unforeseen reasons. Better than <code>302</code> when non-<code>GET</code> operations are available on the site.</td></tr></tbody></table>

\[2\] The specification did not intend to allow method changes, but there are existing user agents that do change their method. [`307`](status/307) was created to remove the ambiguity of the behavior when using non-`GET` methods.

### Special redirections

[`304`](status/304) (Not Modified) redirects a page to the locally cached copy (that was stale), and [`300`](status/300) (Multiple Choice) is a manual redirection: the body, presented by the browser as a Web page, lists the possible redirections and the user clicks on one to select it.

<table><thead><tr class="header"><th>Code</th><th>Text</th><th>Typical use case</th></tr></thead><tbody><tr class="odd"><td><code>300</code></td><td><code>Multiple Choice</code></td><td>Not many: the choices are listed in an HTML page in the body. Machine-readable choices are encouraged to be sent as <a href="headers/link"><code>Link</code></a> headers with <code>rel=alternate</code>.</td></tr><tr class="even"><td><code>304</code></td><td><code>Not Modified</code></td><td>Sent for revalidated conditional requests. Indicates that the cached response is still fresh and can be used.</td></tr></tbody></table>

Alternative way of specifying redirections
------------------------------------------

HTTP redirects aren't the only way to define redirections. There are two others:

1.  HTML redirections with the [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) element
2.  JavaScript redirections via the [DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)

### HTML redirections

HTTP redirects are the best way to create redirections, but sometimes you don't have control over the server. In that case, try a [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) element with its `http-equiv` attribute set to `Refresh` in the [`<head>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head) of the page. When displaying the page, the browser will go to the indicated URL.

    <head> 
      <meta http-equiv="Refresh" content="0; URL=https://example.com/">
    </head>

The `content` attribute should start with a number indicating how many seconds the browser should wait before redirecting to the given URL. Always set it to `0` for accessibility compliance.

Obviously, this method only works with HTML, and cannot be used for images or other types of content.

### JavaScript redirections

Redirections in JavaScript are performed by setting a URL string to the [`window.location`](https://developer.mozilla.org/en-US/docs/Web/API/Window/location) property, loading the new page:

    window.location = "https://example.com/";

Like HTML redirections, this can't work on all resources, and obviously, this will only work on clients that execute JavaScript. On the other hand, there are more possibilities: for example, you can trigger the redirect only if some conditions are met.

### Order of precedence

With three ways to trigger redirections, several ways can be used at the same time. But which is applied first?

1.  HTTP redirects always execute first — they exist when there is not even a transmitted page.
2.  HTML redirects ([`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta)) execute if there weren't any HTTP redirects.
3.  JavaScript redirects execute last, and only if JavaScript is enabled.

When possible, use HTTP redirects and don't add [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) element redirects. If someone changes the HTTP redirects but forgets to change the HTML redirects, the redirects will no longer be identical, which could cause an infinite loop or other nightmares.

Use cases
---------

There are numerous use cases for redirects, but as performance is impacted with every redirect, their use should be kept to a minimum.

### Domain aliasing

Ideally, there is one location, and therefore one URL, for each resource. But there are reasons for alternative names for a resource:

Expanding the reach of your site  
A common case is when a site resides at `www.example.com`, but accessing it from `example.com` should also work. Redirections for `example.com` to `www.example.com` are thus set up. You might also redirect from common synonyms or frequent typos of your domains.

Moving to a new domain  
For example, your company was renamed, but you want existing links or bookmarks to still find you under the new name.

Forcing [HTTPS](https://developer.mozilla.org/en-US/docs/Glossary/https)   
Requests to the `http://` version of your site will redirect to the `https://` version of your site.

### Keeping links alive

When you restructure Web sites, URLs change. Even if you update your site's links to match the new URLs, you have no control over the URLs used by external resources.

You don't want to break these links, as they bring valuable users and help your SEO, so you set up redirects from the old URLs to the new ones.

This technique does work for internal links, but try to avoid having internal redirects. A redirect has a significant performance cost (as an extra HTTP request occurs). If you can avoid it by correcting internal links, you should fix those links instead.

### Temporary responses to unsafe requests

[Unsafe](https://developer.mozilla.org/en-US/docs/Glossary/safe) requests modify the state of the server and the user shouldn't resend them unintentionally.

Typically, you don't want your users to resend [`PUT`](methods/put), [`POST`](methods/post) or [`DELETE`](methods/delete) requests. If you serve the response as the result of this request, a simple press of the reload button will resend the request (possibly after a confirmation message).

In this case, the server can send back a [`303`](status/303) (See Other) response for a URL that will contain the right information. If the reload button is pressed, only that page is redisplayed, without replaying the unsafe requests.

### Temporary responses to long requests

Some requests may need more time on the server, like [`DELETE`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/DELETE) requests that are scheduled for later processing. In this case, the response is a [`303`](status/303) (See Other) redirect that links to a page indicating that the action has been scheduled, and eventually informs about its progress, or allows to cancel it.

Configuring redirects in common servers
---------------------------------------

### Apache

Redirects can be set either in the server config file or in the `.htaccess` of each directory.

The `mod_alias` module has `Redirect` and `RedirectMatch` directives that set up [`302`](status/302) redirects by default:

    <VirtualHost *:443>
        ServerName example.com
        Redirect / https://www.example.com
    </VirtualHost>

The URL `https://example.com/` will be redirected to `https://www.example.com/`, as will any files or directories under it (`https://example.com/some-page` will be redirected to `https://www.example.com/some-page`)

`RedirectMatch` does the same, but takes a [regular expression](https://developer.mozilla.org/en-US/docs/Glossary/regular_expression) to define a collection of affected URLs:

    RedirectMatch ^/images/(.*)$ https://images.example.com/$1

All documents in the `images/` directory will redirect to a different domain.

If you don't want a temporary redirect, an extra parameter (either the HTTP status code to use or the `permanent` keyword) can be used to set up a different redirect:

    Redirect permanent / https://www.example.com
    # …acts the same as: 
    Redirect 301 / https://www.example.com

The `mod_rewrite` module can also create redirects. It is more flexible, but a bit more complex.

### Nginx

In Nginx, you create a specific server block for the content you want to redirect:

    server {
        listen 80;
        server_name example.com;
        return 301 $scheme://www.example.com$request_uri;
    }

To apply a redirect to a directory or only certain pages, use the `rewrite` directive:

    rewrite ^/images/(.*)$ https://images.example.com/$1 redirect;
    rewrite ^/images/(.*)$ https://images.example.com/$1 permanent;

### IIS

In IIS, you use the `<httpRedirect>` element to configure redirections.

Redirection loops
-----------------

Redirection loops happen when additional redirections follow the one that has already been followed. In other words, there is a loop that will never be finished and no page will ever be found.

Most of the time this is a server problem, and if the server cannot detect it, it will send back a [`500`](status/500) `Internal Server Error`. If you encounter such an error soon after modifying a server configuration, this is likely a redirection loop.

Sometimes, the server won't detect it: a redirection loop can spread over several servers which each don't have the full picture. In this case, browsers will detect it and display an error message. Firefox displays:

> Firefox has detected that the server is redirecting the request for this address in a way that will never complete.

…while Chrome displays:

> This Webpage has a redirect loop

In both cases, the user can't do much (unless a corruption is happening on their side, like a mismatch of cache or cookies).

It is important to avoid redirection loops, as they completely break the user experience.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Redirections$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Redirections" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Redirections</a>
