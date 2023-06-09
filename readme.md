# async-handler-ts

`async-handler-ts` provides a utility function for handling asynchronous operations in TypeScript. It simplifies the process of error handling and result extraction, allowing you to write cleaner and more concise code.

## Installation

You can install `async-handler-ts` via npm or yarn:

```bash
npm i async-handler-ts

# or

yarn add async-handler-ts
```

## Usage

To use `async-handler-ts`, import the `asyncHandler` function from the package:

```typescript
import { asyncHandler } from "async-handler-ts"
```

The `asyncHandler` function takes a single argument, which is the asynchronous function you want to handle. It returns a promise that resolves to a tuple (array of just two elements) containing the result and error (if any) of the function execution.

Here's an example of how to use `asyncHandler`:

```typescript
async function fetchData(): Promise<string> {
  // Simulating an asynchronous operation
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("Data fetched successfully")
    }, 1000)
  })
}

async function main() {
  const [result, error] = await asyncHandler(fetchData())
  if (error) {
    console.error("An error occurred:", error)
  } else {
    console.log("Result:", result)
  }
}

main()
```

By wrapping your function with `asyncHandler`, you can conveniently handle any errors that occur during its execution. 

If the asynchronous function succeeds, the `result` variable will hold the resolved value, and `error` will be `undefined`. Conversely, if an error is thrown or the promise is rejected, `result` will be `undefined`, and `error` will contain the thrown error.

## Contribution

Contributions to `async-handler-ts` are welcome! If you encounter any issues, have suggestions, or would like to add new features, please open an issue or submit a pull request on the [GitHub repository](https://github.com/DevOsamaIslam/async-handler-ts).

## License

This project is licensed under the [MIT license](https://github.com/DevOsamaIslam/async-handler-ts/blob/master/LICENSE).
