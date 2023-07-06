# ts-calc

Full-typescript calculator foe exercise purposes. Idea and rules taken from this article
https://blog.kbdev.io/dev/2021/10/05/type-calculator.html

### The rules

If you want to try to do the calculator, here are the rules of the “game” (if we can call this a game):

- you have to start with only two types: BZero (for Boolean Zero) and BOne (for Boolean One).

```ts
type BZero = false;
type BOne = true;
```

- you can only use types. No interface, no enum, only types.
- you have to compute the four basic mathematical operations (with types): add, subtract, multiply and divide. You can also add modulo.
  this code should works:

```ts
// Equivalent of (6 + 6 * (1 + 2)) / (6 - 2) = 6
type StrangeOperation = Divide<
  Add<Multiply<Six, Add<One, Two>>, Six>,
  Subtract<Six, Two>
>;
```

Due to the way I implement the calculator, I use another type Result to read the result:

```ts
type OpResult = Result<StrangeOperation>;
```

This type is totally optional in the rules. But you must have a exact number type at the end of the computation. For example, you should have:

```ts
type OpResult = 6;
```

And here you go! It’s time for you to code!
