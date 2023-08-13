### Chapter 2: Hello TypeScript

#### Introduction:
- This chapter provides hands-on experience with the first TypeScript program and the compiler CLI command.
- It explores how the compiler-emitted JS code changes based on JS language level and module type.
- The chapter examines a simple program's compiled output, including the type declaration file.

#### Anatomy of the Project:
- A basic TypeScript project consists of three main files:
  1. `package.json`: The package manifest.
  2. `tsconfig.json`: Contains TypeScript compiler settings.
  3. `src/index.ts`: Represents the main program.

#### Running the Compiler:
- The `dev` script in `package.json` runs the TypeScript compiler in “watch” mode. This mode watches for source changes and rebuilds automatically.
- The command used is `tsc --watch --preserveWatchOutput`.

#### Changing Target Language Level:
- The `tsconfig.json` file contains the `compilerOptions.target` property, which determines the JavaScript version to target.
- By default, the target is set to `ES3`, which is suitable for older browsers like IE6.
- Changing the target to `ES2015` introduces modern language features like promises and generator functions.
- Setting the target to `ES2017` uses the `async` and `await` keywords, making the output more similar to the original TypeScript code.

#### Code Examples:
1. **Timeout Function**:
   ```typescript
   /**
    * Create a promise that resolves after some time
    * @param n number of milliseconds before promise resolves
    */
   function timeout(n: number) {
       return new Promise((res) => setTimeout(res, n));
   }
   ```

2. **Add Numbers Function**:
   ```typescript
   /**
    * Add two numbers
    * @param a first number
    * @param b second number
    */
   export async function addNumbers(a: number, b: number) {
       await timeout(500);
       return a + b;
   }
   ```

   - This function is asynchronous and returns a promise.
   - It waits for half a second and then adds the numbers `a` and `b`.
   - When executed, there should be a half-second delay before the result is printed to the console.

#### Types of Modules:
- Node.js expects CommonJS modules. Therefore, to make the TypeScript code compatible with Node.js, the `tsconfig.json` file should include the property `"module": "CommonJS"`.
- The way functions (like `addNumbers`) are exported changes based on the module type.

#### Conclusion:
- After setting up the project correctly and making necessary adjustments in the `tsconfig.json` file, running the program with Node.js should print the result `7` to the console after a short delay.
