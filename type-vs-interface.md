
# Type Alias vs Interface in typeScript

## Introduction

TypeScript provides two ways to define custom types: Type Aliases and Interfaces. Both help developers describe the structure of data and make code more readable and maintainable. However, they have some important differences.

## Detailed Explanation

A Type Alias uses the `type` keyword to create a name for any type. It can define primitive types, objects, unions, intersections, and tuples.

``typescript
type User = {
    name: string;
    age: number;
};

type Status = "active" | "inactive";
```

An Interface uses the `interface` keyword to define the structure of an object. It is commonly used when describing objects and class structures.

```typescript
interface Student {
    name: string;
    age: number;
}
```

One major difference is declaration merging. Multiple interfaces with the same name can be combined automatically.

```typescript
interface Person {
    name: string;
}

interface Person {
    age: number;
}
```

Now, the `Person` interface contains both properties. Type Aliases do not support this feature.

Both interfaces and type aliases support extending object structures. Interfaces use `extends`, while type aliases can combine structures using intersection (`&`).

## Conclusion

Both approaches are useful in TypeScript. Interfaces are generally suitable for object structures and extensible contracts, while Type Aliases are more flexible for unions, tuples, and other complex types. Choosing between them depends on the requirements of the project.
