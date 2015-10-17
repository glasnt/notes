Douglas Crockford - JavaScript the Better Parts

[https://www.youtube.com/watch?v=rhV6hlL_wMc](https://www.youtube.com/watch?v=rhV6hlL_wMc)

We are not paid to use every feature of the language

"Good Parts" is still a best seller

Obscure bug - `.` can be equiv to `=` -> being fixed in JSLint

The Story behind `===`:
 * `==` - equality with type coersion
 * Brendan Eich realised it was bad to always imply type coersion. 
 * The fix to `==` made JS run faster
 * standards committee didn't accept the fix because of legacy, backwards compatibility
 * new code was created as the `===` function

Foot Guns - Something you can shoot yourself in the foot with

New Good Calls
 - proper tail calls (funcrional programming). Instead of call return, jump
 - elipsis replace arguments array (code example in video at 12:20)
 - Modules - global object
 - let is the new var - block scope is now a thing

Destructuring

weakmap - worst name ever

keys as strings was a mistake

new kind of object

new type of class
 - will be bad
 - for java devs who now have to learn javascript because there are no java jobs
 - functional programming 4lyf

fat arrow - remove the word 'function'
 - should allow `(name) => {id:name}`, but it's currently broken

make the language smaller

"this" is pair programming with abbott and costello

new good bits - 
 - don't use `new`, `object`, `this`, `null`

 
security++ AdSafe
 - can't make it safe, make it illegla

`typeof(null)` = `object`

don't use falsey value - 0, "", NaN
 - use `=== undefined`

dont use for loops 
 - use array.forEach (introduced in ES5)
 
map is now a thing

object.keys instead of for in 


ES6 -> use fat calls not while

`forEach` is not the same as `for`

Programming had to choose between smalltalk and c++, c++ won, which is why a lot of things resemble it
 - ruby is more like smalltalk

it took a generation for people to realise that X was a Y idea: 
 - high level languages good
 - goto bad
 - objects good
 - lambda good (2 generations)

System languages vs Application languages
 - there hasn't been a lot of innovation with system languages

Prototypal Inheritance

In ES6 - Class Free Object Oriented Programming

Block scope + function scope -> Closure


First popular language to use Lambda = JavaScript

New way of programming

```
function constructor(spec) { 
	let {member} = spec, 
	    other = other_constructor(spec), 
            method = function() { ... };

 	return Object.freeze({method, other});
}
```
 - variable expansion means that spec doesn't have to be strictly defined
 - return a bunch of frozen methods that cna't be tampered with -> security


