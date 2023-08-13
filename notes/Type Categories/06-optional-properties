### Chapter 6: TypeScript - Optional Properties

#### Optional Properties:
- TypeScript introduces the concept of optional properties.
- These properties, denoted with the `?` symbol, might not always be present.
  ```typescript
  interface Car {
    make: string;
    model: string;
    year: number;
    chargeVoltage?: number;  // Optional property
  }
  ```
  - The `chargeVoltage` property is optional and might be absent unless the car is electric.
- There's a distinction between an optional property and a property that can have an `undefined` value. Optional properties can be left out, but if a property can have an `undefined` value, it must be explicitly set to `undefined`.

#### Excess Property Checking:
- TypeScript performs excess property checking on object literals.
- If an object literal has properties that aren't defined in the type, TypeScript will raise an error.
  ```typescript
  const myCar: Car = {
      make: "Toyota",
      model: "Camry",
      year: 2020,
      color: "red"  // Error: 'color' does not exist in type 'Car'
  };
  ```
- The error message indicates that the object literal may only specify known properties.
- This feature ensures that developers don't accidentally add properties that aren't part of the defined type.

#### Handling Excess Properties:
- One way to handle excess properties is to make them optional in the type definition.
- Another approach is to use type assertions to tell TypeScript to treat the object as a specific type.

#### Type Guards:
- TypeScript provides type guards, which allow developers to create branches of code where the compiler can understand the type of a variable.
- For example, checking if a variable is defined before using it.
  ```typescript
  if (car.chargeVoltage) {
    console.log(car.chargeVoltage.toFixed(2));
  }
  ```
- This is called a type guard, and it ensures that the variable is of the expected type before using it.

#### Conclusion:
- TypeScript's type system provides robust mechanisms to ensure type safety and code correctness.
- Optional properties and excess property checking are powerful features that help developers write clean and error-free code.
- Developers should be aware of these features and use them effectively to avoid potential pitfalls.


# Additional


### Optional Property vs. Property with Undefined Type:

1. **Clarity and Intent**:
   - **Optional Property**: Denoted with the `?` symbol, it clearly indicates that the property is optional and may or may not be present in the object. It's a direct way to convey the intent that the property is optional.
   - **Property with Undefined Type**: Requires the property to be explicitly set to `undefined` if it's not present. While it can be more verbose, it ensures that the property's potential absence is explicitly acknowledged.

2. **Type Safety**:
   - Both approaches ensure type safety. However, with the `undefined` type, the property's potential to hold an `undefined` value is explicitly stated.

3. **Use Cases**:
   - **Optional Property**: Ideal for properties that might be absent in some instances of the object but present in others. E.g., a `middleName?` in a `Person` interface.
   - **Property with Undefined Type**: Suited for scenarios where you want to ensure that a property is always acknowledged, even if its value is `undefined`. This can be useful in configurations or settings where every property's presence is crucial.

### Personal Conclusion:

For most scenarios, using optional properties (`?`) is more concise and clear. However, if there's a need to ensure that a property is always addressed or acknowledged, even if its value is `undefined`, then using a property with an `undefined` type might be more appropriate.

