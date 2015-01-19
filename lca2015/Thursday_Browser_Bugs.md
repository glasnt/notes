Roan Kattow - Wikimedia Foundation

full slides: tinyurl.com/browserbugslca15

web developement was hard, jquery good

debugging via alerts bad, concsoles good

animated titles - netscale 2 - duplicate title tags -> looks like animation

browsers have bugs

(Bugs found based on work with Visual Editor - https://en.wikipedia.org/wiki/Wikipedia:VisualEditor)

Chrome: 
 - interactive box shadow
 - caching
 - fonts
 - highlight UL/LI wrong - double blue

JS bugs - array splice length limit: 
 - chrome 2^17
 - firefox 2^19
 - safari 2^16
 - IE9 - 2^25 and explosions

 Solution: when using `splice.apply()` do in 1024 or smaller

No crash ~= correct - array splice ops broken

Firefox has bugs too 
 - bottom-padding + scrollable - 12 year old bug
 - iframe hack - document write

Lag bugs in IE8

regex types out of objects =(

Opera now = skinned chrome

DOM parser - HTML Parsing


IE 
 - speaker has contact in team, actively attempting to fix bugs)
 - colour + RTL -> invisibility
 - set attribute != get attribute
 - invalid css -> empty string; empty string -> null


pre strips first new line -> iterative stripping
 - broken in all BUT opera12... which is EOL

 krinkle.github.io/dom-ce

responsiveness to bug submissions
 - IE now ok-ish because wikipedia (super/sub script, UL/LI, RTL, LTR - all heavily used)
 - FF ~ok
 - Chrome - none

