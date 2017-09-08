# typescript-definition-generator
Work in Progress - Generates definitions from JS files declaring nested variables using esprima

Takes advantage of https://www.typescriptlang.org/docs/handbook/declaration-merging.html

E.g. given

```js
(function() {
myns.foo = {
	/** @param {string} a */
	bar: function(a) {
		return (expr);
	}
}
}());
```

Should emit the following

```js
interface myNS___Interface {
	foo: MyNS___foo___Interface;
}
interface myNS___foo___Interface {
	bar: (a: string) => any
}
```
