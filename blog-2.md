# How Generics Help Build Reusable and Type-Safe Code in TypeScript

## Introduction

Generics are one of the most powerful features of TypeScript. They allow developers to write reusable functions, classes, and components while keeping strong type safety.

Without generics, developers often need to write the same logic multiple times for different data types.

## Problem Without Generics

Example without generics:

```ts
function getString(value: string): string {
  return value;
}

function getNumber(value: number): number {
  return value;
}
````

The logic is the same, but we are repeating code.

## Using Generics

Generics solve this problem.

```ts
function getValue<T>(value: T): T {
  return value;
}
```

Now the same function works with different data types.

```ts
getValue<string>("Hello");
getValue<number>(100);
```

## Benefits of Generics

### 1. Reusable Code

One generic function can work with many data types.

### 2. Type Safety

TypeScript still checks the correct type.

```ts
function identity<T>(data: T): T {
  return data;
}

const result = identity<number>(50);
```

Here, `result` will always be a number.

### 3. Cleaner Code

Generics reduce duplication and improve readability.

## Generics with Interfaces

```ts
interface ApiResponse<T> {
  success: boolean;
  data: T;
}

const userResponse: ApiResponse<string> = {
  success: true,
  data: "John",
};
```

This makes interfaces flexible and reusable.

## Conclusion

Generics help developers create reusable, scalable, and type-safe applications. They reduce duplicate code and improve maintainability. In TypeScript projects, generics are very important for writing clean and professional code.