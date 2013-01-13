I was using CoreText to draw some monospace text. However, I found the result is not right when some fonts are used. The monotype font turns out to be not monospaced. Some characters are close to each other like kerning is on. But the fonts does not have kerning, and I use kCTKerningAttributeName to disable kerning.
It turns out that iOS has another method to adjust spaces bwtween characters called ligature. The concept of ligature can be get at http://en.wikipedia.org/wiki/Typographic_ligature .

So the solution is simple, just set kCTLigatureAttributeName to 0.