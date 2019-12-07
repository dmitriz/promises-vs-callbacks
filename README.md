# promises-vs-callbacks
JS promise is not a replacement for callbacks

### Don't confuse callbacks as clean and powerful pattern with Node API

The continuation-passing-style behind callbacks is one of the oldest and most fundamental functional patterns used across most programming languages. It is the simplest way to write async code without any extra stuff other than functions. Callback style provides a unified functional way of writing database interactions, HTTP requests, streams, websockets, event listeners etc. 
In JavaScript, where functions are variadic by design, [this pattern can be made yet more powerful with functions accepting any number of callbacks](https://github.com/dmitriz/cpsfy/blob/master/DOCUMENTATION.md#variadic-input-and-output). Finally, a clean functional composition for callback-style functions is [easily achievable with few simple convenience operators](https://github.com/dmitriz/cpsfy).


### The so-called "callback hell" is an issue with Node API, not callbacks

The Node API is a very specific way of using callbacks. Node API callbacks are mixed along with other arguments with no clean separation between in- and outgoing data. Node API callbacks receive the error argument ahead of others making it less convenient to defer the error handling. This lack of convenience is very specific to that particular style though.


### JS Promises are really a collection of opinionated convenience methods

There is no question about promises being convenient in many simple situations. Making them perfectly legitimate to use in those cases. There is also no question about their [numerous problems](https://medium.com/@avaq/broken-promises-2ae92780f33). Making them unsuitable or dangerous for many other cases and a bad paradigm to advocate for when not accompanied by clear warnings about those dangers and limitations. Promises aren't suitable or too cumbersome for streams, websockets, event listeners or anything more advanced than single request-response. The fact that promise is more of a convenience choice than something fundamental is illustrated by their lacking presence anywhere beyond JavaScript and their [lacking conformity to general functional paradigms](https://stackoverflow.com/a/50173415/1614973). And even in JavaScript, it is illustrated by the need of further syntax improvements such as `async/await`.


### We must acknowledge promise was a wrong choice as primitive and move on

The fact that promises are simple and convenient in many simple cases doesn't make them a good choice as primitive replacing callbacks:

https://github.com/promises-aplus/promises-spec/issues/94#issuecomment-553767177
> 1. The things done wrong here are fundamental to programming/computation itself, so there will never be a time when it is not wrong. And probably never be a time when it doesn't adversely effect programming in Javascript/Typescript.
> 2. Those who think the conclusions here are OK will never search it up. This thread is kept alive by those who encountered the wrongness and searched the web for what went wrong.

Creating primitives that are more fundamental, powerful, composable and flexible than promises, that are universal accross languages and backed by science is [not hard](https://github.com/dmitriz/cpsfy). There is no excuse for getting stuck with promises. We need to move on.
