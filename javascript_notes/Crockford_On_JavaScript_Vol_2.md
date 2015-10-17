[https://www.youtube.com/watch?v=RO1Wnu-xKoY](https://www.youtube.com/watch?v=RO1Wnu-xKoY)


The Big Bang -> The Dawn of Man -> JavaScript

Without the history, you are consumed by mythology
New innovations are met with contempt

The first important discovery of the 21st century - js has good parts

National Center of Supercomputing Applications - Mosaic
 - www
 - ftp
 - gopher

Mosaic: X Window System - Microsoft Windows - Macintosh
 - Added image tags because they could, Tim Berners-Lee didn't particularly want it
 - University of Illonis students -> Netscape

Netscape was more popular becuase they ignored TBL
 - cookies, format tags, links, interactivity

They wanted interactivity to work like Hypercard

"I want to write scheme" 'You're hired!' ... 'Oh, that's what scheme is? We don't like it, make it like what people like'

Originally - LiveScript 
 - based on scheme (which was LISP), self (which was smalltalk)
 - netscape nagivator 2  would have scripting, plus livewire server had javascript
 - we want java, we want livescript - "well, let's change the name to javascript" - possibly said as a joke

Sun tried to kill livescript. In the rename, sun got the trademark even though they had nothing to do with it

netscape wanted to kill microsoft

The software that is going to destory microsoft is windows mobile

mirosoft reverse engineerd javascript (because trademark) called it jscript

netscape got scared, went to w3c to try and get things standardised, w3c said go away

netscape went around to all the places, ended up to ECMA (european)
 - heaps of companies on the place

We want a standard for thislanguage, but we can't call it javascript. Working name = ECMAscript

JavaScript is a trademark now of Oracle

We should call it Ecmascript, but that's an awful name

**note, this video is from 2011, ES6 is in the works now**

1999 ES3 Third edition

2009 ES5 Fifth edition
 - default 
 - strict

For the forst time , work in the eintersection of es3 and es5/strict
 - avoid es5/default

Where do the bad parts come from?
 - legacy
 - good intentions
 - haste

 - for the most part, the bad parts can be avoided
 - the problem with the bad parts isn't it that they are useless
 - you can avoid the bad parts, and there's some awesome things in there

A long line of sinnage that were inherited

Implied global variables, semicolon insertion

If you have no idea, you can still generally make things work. It works against professional programmers

Smalltalk - 8 years. JavaScript - 8 days. 

Had netscape been a better managed company, we may not have to be dealing with it now

Most people don't bother to learn JS before they use it. They assume they don't need any knowldge

The badparts aren't useless, they are dangerous

"Oh, i found anohter thing to do with eval" - ... "stop doing that!"

in JS - an object isa dynamic collection of properties
 - every properly has a key string which is unique within that object
 - get, set, and deelete

object.name == object[name]

Propery 
 - value, writable, enumerable, configurable
 - new in ES5 - get and set
 - first four were always there, but never exposed. Fixed in ES5



ES5 compatibility - http://kangax.github.io/compat-table/es5/

other languages have initialisers, object literals means you can create your own

accessor property - get or set
 - hazardous
 - don't get stupid wiht this stuff
 - use it sparingly
 - reasons: the DOM does this, we want to wrap it and tame it
 - We have to fix the DOM, and it's awful

Classes vs Prototypes
 - JavaScript is class free - it uses prototypes

Classes
 - first made in 1967 Simula
 - small talk took this model 

Prototype code is smaller
 - make an object you like
 - create new instances that inhert from that obkect
 - customise the new objects
 - taxonomy and classification are not nessessary


If you're classifying a system, you'renot likely to understand the entire thing. You'll end up with cruft

Delegation - differential inheritence
 - objects inherit, and only store the differnces (otherwise it delegates upwards)

Prototype
 - object or `null`
 - ES5 - `object.create()`
 - ES5 - `object.getPrototypeOf(object)`
  - "Do you have what I need? Yes: yay. No: exception"

`new` prefix operator
 - psudo code: 
```
function new(func, arguments) { 
	var that = Object.create(function.prototyoe)
	var result = func.apply (that, arguments); 
	return (typeof result === 'object' && result ) || that
}
```

You don't need to use `new` anymore, just object.create
 - if you forget `new`, you clobber the global object
 - no compile time warning, no run time warning

Problem with JavaScript - reserved words as keys
 - e.g. `if (func[word])` is truthy if `func` has a contrustor
 - e.g. `if object.hasOwnProperly` in for in enumeration
 - you have to check the value and the type of the value
 - solved in ES5 - can inherit from null, so nothing - no base object stuffs

JavaScript keys must be string

Extensible - boolean
 - isExtenible 
 - prevent Extensions
 - seal (turn off configs), freeze (also sets read only)
 --> immutable objects :D

Objects and: number, string, array, date, regexp

### Numbers

 - only IEEE-754 floats (java calls it Double (becuase double precision))
 - No integers.
 - all numbers. ergo, technically an array index is a float. 
 

Assosicativiety Law does not hold
 - `a + b + c === (a + b) + c === a + (b + c)`
 - doesn't hold in javascript
 - x + x = 1 for x > 9 quadrillion
 - 0.1, 0.2, 0.3 => additions don't fold. 

```
>>> a = 0.1;
0.1
>>> b = 0.2;
0.2
>>> c = 0.3;
0.3
>>> (a + b) + c === a + (b + c)
false

```

You have the ability to extend the language, and update the primary types. 
 - AJAX libraries should be able do to this
 - A general programmer shouldn't

Numbers are first class
 - stored in an variable
 - passed as a param
 - returned from a function
 - stored in an object

Math Object
 - abs, acos... sqrt, tan
 - should have been methods of number, but they aren't

NaN
 - Not a Number
 - .. but it is actually a number
 - `NaN === NaN` > false
 - `NaN !== NaN` > true
 - toxic - NaN as input -> NaN as a result


### Boolean
