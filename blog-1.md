# Why `unknown` is Safer than `any` in TypeScript

## Introduction

TypeScript provides different data types to make code safer and easier to manage. Two important types are `any` and `unknown`. Many beginners use `any` because it removes type checking, but it can create problems in large projects. The `unknown` type is safer because it forces developers to check the type before using the value.

## Why `any` is Called a Type Safety Hole

The `any` type disables TypeScript checking. This means any value can be assigned and used without validation.

```ts
let value: any = "Hello";
value = 100;
value.toUpperCase();
````

In the example above, TypeScript will not show an error even though `toUpperCase()` cannot be used on a number. This can cause runtime errors.

Because `any` ignores type safety, it is called a “type safety hole.”

## Why `unknown` is Safer

The `unknown` type also accepts any value, but TypeScript does not allow unsafe operations directly.

```ts
let value: unknown = "TypeScript";

if (typeof value === "string") {
  console.log(value.toUpperCase());
}
```

Here, we first check whether the value is a string. After checking, TypeScript allows string methods.

This process is called type narrowing.

## What is Type Narrowing?

Type narrowing means reducing a broad type into a specific type using conditions.

Common ways:

* `typeof`
* `instanceof`
* Equality checking

Example:

```ts
function printValue(value: unknown): void {
  if (typeof value === "number") {
    console.log(value.toFixed(2));
  }
}
```

TypeScript understands that `value` is a number inside the condition block.

## Conclusion

The `any` type removes safety and may create hidden bugs. The `unknown` type is safer because it requires type checking before use. In modern TypeScript projects, developers should prefer `unknown` when handling unpredictable data.
````
