# no-jquery

This library (if you can call it that) does a very simple thing: restoring the
original value of `$` and removing `jQuery` from the global `window` object.
  
## Why?

That's a good question. It sounds like a silly idea to include jQuery and then
use another *library* just to remove it, but sometimes it could be useful.

One use case is for when you need to include jQuery up to a certain
point, and then make sure that it's no longer used by subsequent scripts. In
my case, I wanted jQuery to be available for my `Chai` assertions using 
[`chai-jquery`](https://github.com/chaijs/chai-jquery), but not within the
application code itself. Using `chai-jquery` for DOM assertions is convenient,
but I don't need jQuery in my application, and want to make sure that any 
libraries that I use don't find jQuery on the global scope and try to use it 
during test execution. Also, if I were to use jQuery in my application, I'd
include it as a dependency through Bower, meaning that during test execution
jQuery would try to load twice, and that could be nasty! 

## Install

Use bower:

```
bower install no-jquery --save-dev
```

Or NPM:

```
npm install no-jquery --save-dev
```


## Usage

Just include the script in the right place.