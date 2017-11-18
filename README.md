# rfc-js-bind-destructuring
A proposal for JS bind operator (https://github.com/tc39/proposal-bind-operator) with destructuring.

We should be able to destructure with binding operator:

```js
const { ::log } = console
```

Equivalent to:

```js
const log = console.log.bind(console)
```

---

To be determined how to interact with nested desctructuring, but either:

(A) Bind to direct parent:

```js
const { foo: { ::bar } } = target
```

Equivalent to:

```js
const bar = target.foo.bar.bind(target.foo)
```

Or (B) bind to root target of destructuring:

```js
const { foo: { ::bar } } = target
```

Equivalent to:

```js
const bar = target.foo.bar.bind(target)
```
