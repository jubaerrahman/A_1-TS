
# Type Narrowing in TypeScript

## Introduction

Type Narrowing is a important feature of TypeScript that allow developers to reduce a variable's posible types within a specific section of code. It helps handle union types safly and prevent type related errors during developement.

## Detailed Explanation

TypeScript use different techniques to narrow types. One common technique is the `typeof` operator, which check primitive data types such as strings, numbers, and booleans.

```typescript
function processValue(value: string | number): void {
    if (typeof value === "string") {
        console.log(value.toUpperCase());
    } else {
        console.log(value * 2);
    }
}
```

Another usefull technique is `instanceof`. It checks wheather an object belong to a particular class.

```typescript
class Car {
    drive(): void {
        console.log("Driving");
    }
}

function startVehicle(vehicle: Car | Date): void {
    if (vehicle instanceof Car) {
        vehicle.drive();
    } else {
        console.log(vehicle.getFullYear());
    }
}
```

The `in` operator check whether a particular property exist in an object. It is useful when working with diffrent object strucutres.

```typescript
type Admin = { name: string; permissions: string[] };
type User = { name: string; email: string };

function getInfo(person: Admin | User): void {
    if ("permissions" in person) {
        console.log(person.permissions);
    } else {
        console.log(person.email);
    }
}
```

In each example, TypeScript understand the type more precisley inside the relevant conditional block.

## Conclusion

Type Narrowing make TypeScript applications safer and easier to maintain. Using `typeof`, `instanceof`, and the `in` operator help developers work with multiple types without relying on unsafe type assertions.