# [searching text in HTML spans with absolute positions](https://groups.google.com/a/chromium.org/g/chromium-discuss/c/KBT__5UhptE)

searching for the text "1 2 3"  
in the html spans

```html
<span>1</span>
<span>2</span>
<span>3</span>
```

fails when the spans have  
`style="position:absolute"`

also: clipboard text has no whitespace between words

also: triple-click does not select the whole paragraph

also: text-selection highlight has too much height above the selected text in spans with relative positions.
the text-selection highlight starts at the relative position y=0

with chromium 137.0.7151.119  
this works with SVG tspan elements  
but not with HTML span elements

repro:  
https://milahu.github.io/chromium-discuss-text-search-absolute-position-spans/test.html  
https://milahu.github.io/chromium-discuss-text-search-absolute-position-spans/test2.html

use case:  
EPUB-FXL = fixed-layout EPUB  
useful for scanned books  
allows better compression than PDF  
https://github.com/internetarchive/archive-hocr-tools/pull/23

related:  
https://stackoverflow.com/questions/62381455  
How Do I make my HTML searchable by a browser Ctrl-F and use absolute text positioning?



## [text-selection has too much height in spans with relative positions](https://groups.google.com/a/chromium.org/g/chromium-discuss/c/JKN3cuHp-l8)

minimal example:

```html
<div>
 <span>1</span>
 <span style="position: relative; top: 2em">2</span>
</div>
```

https://milahu.github.io/chromium-discuss-text-search-absolute-position-spans/issue4.html

complex example:

https://milahu.github.io/chromium-discuss-text-search-absolute-position-spans/test2.html

reproduce:  
select text in spans with relative positions

actual:  
text-selection highlight has too much height  
above the selected text  
in spans with relative positions.  
the text-selection highlight  
starts at the relative position y=0

expected:  
text-selection highlight should have the same height  
as with selected text in spans with absolute positions

this fails in chrome 137.0.7151.119  
this works in firefox 139.0.4-1

use case:  
EPUB-FXL = fixed-layout EPUB
