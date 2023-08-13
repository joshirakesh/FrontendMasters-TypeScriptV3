### Chapter 8: TypeScript - Arrays & Tuples

#### Arrays:
- Arrays are a fundamental collection type in JavaScript.
- Arrays can be typed to ensure each element conforms to a specific type.
  ```typescript
  const fileExtensions: string[] = ["js", "ts"];
  ```

- Arrays can also be defined for more complex types:
  ```typescript
  const cars: {
    make: string;
    model: string;
    year: number;
  }[] = [
    {
      make: "Toyota",
      model: "Corolla",
      year: 2002
    }
  ];
  ```

#### Tuples:
- Tuples are like arrays, but each position has a specific type and meaning.
- They can be used to represent structured data without creating a formal type.
  ```typescript
  const carTuple: [number, string, string] = [2002, "Toyota", "Corolla"];
  ```

- Destructuring can be used with tuples to extract individual elements:
  ```typescript
  const [year, make, model] = carTuple;
  ```

- TypeScript requires explicit type annotations for tuples since it defaults to inferring arrays.
  
#### Limitations and Enhancements:
- While tuples provide type safety on assignment, they don't prevent array-like operations that can change their structure.
  ```typescript
  carTuple.push("Sedan");  // This is allowed, even if not intended.
  ```

- However, TypeScript introduced the `readonly` modifier to make tuples immutable:
  ```typescript
  const readonlyCarTuple: readonly [number, string, string] = [2002, "Toyota", "Corolla"];
  readonlyCarTuple.push("Sedan");  // Error: Property 'push' does not exist on type 'readonly [number, string, string]'.
  ```

- This enhancement ensures that tuples remain as intended, preventing unintended modifications.

#### Future of JavaScript and TypeScript:
- There's a proposal for real records and tuples in JavaScript.
- The JavaScript community, especially TC 39 (the committee that decides JavaScript's future), is unlikely to make JavaScript a statically typed language.
- The current approach works well, with JavaScript being a compiled target.
- WebAssembly might be a future direction, where other typed languages compile out to WebAssembly bundles.
