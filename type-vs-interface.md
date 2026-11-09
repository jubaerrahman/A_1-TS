# Type Alias vs Interface in TypeScript

## Introduction

TypeScript gives us two ways to create custom types: Type Alias and Interface. Both are used to define the structure of data and make our code easier to understand. Although they have similar uses, there are some differences between them.

## Detailed Explanation

A Type Alias is created using the `type` keyword. It can be used for different types of data, including primitive types, objects, unions, intersections and tuples.

```typescript
type User = {
    name: string;
    age: number;
};

type Status = "active" | "inactive";
```

On the other hand, an Interface is created using the `interface` keyword. It is mainly used to describe the structure of objects.

```typescript
interface Student {
    name: string;
    age: number;
}
```

One important difference is declaration merging. We can declare multiple interfaces with the same name, and TypeScript will combine their properties.

```typescript
interface Person {
    name: string;
}

interface Person {
    age: number;
}
```

Now the `Person` interface contains both `name` and `age` properties. But Type Aliases do not support declaration merging.

Both Type Aliases and Interfaces can also extend object structures. Interfaces use the `extends` keyword, while Type Aliases can use intersection (`&`) to combine types.

## Conclusion

Both Type Alias and Interface are useful in TypeScript. Interfaces are mostly suitable for defining object structures, while Type Aliases are more flexible for unions, tuples and other complex types. We can choose either one depending on our project requirements.