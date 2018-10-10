# JavaScript Interview common questions

This repo is dedicated for common interview questions of JavaScript which developers have faced during their past interviews. 

#### What would the following code return?

```
console.log(typeof typeof 1);

Answer:

string

typeof 1 will return "number" and typeof "number" will return string.
```

#### What is the value of typeof undefined == typeof NULL?

> The expression will be evaluated to true, since NULL will be treated as any other undefined variable.
>
> Note: JavaScript is case-sensitive and here we are using NULL instead of null.



## Imagine you have this code:

```
var a = [1, 2, 3];

a. Will this result in a crash?

	a[10] = 99;
	
b. What will this output?
	
	console.log(a[6]);
```

a) It will not crash. The JavaScript engine will make array slots 3 through 9 be “empty slots.”

b) Here, a[6] will output undefined, but the slot still remains empty rather than filled with undefined. This may be an important nuance in some cases. For example, when using map(), empty slots will remain empty in map()’s output, but undefined slots will be remapped using the function passed to it:

```javascript
var b = [undefined];
b[2] = 1;
console.log(b);             // (3) [undefined, empty × 1, 1]
console.log(b.map(e => 7)); // (3) [7,         empty × 1, 7]
```