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

with chromium 137.0.7151.119  
this works with SVG tspan elements  
but not with HTML span elements

repro:  
https://milahu.github.io/chromium-discuss-text-search-absolute-position-spans/test.html

use case:  
EPUB-FXL = fixed-layout EPUB  
useful for scanned books  
allows better compression than PDF  
https://github.com/internetarchive/archive-hocr-tools/pull/23

related:  
https://stackoverflow.com/questions/62381455  
How Do I make my HTML searchable by a browser Ctrl-F and use absolute text positioning?
