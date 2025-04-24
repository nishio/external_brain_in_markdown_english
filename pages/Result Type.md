---
title: "Result Type"
---

Type for functions that can fail to return failure information
[[Rust]] is pulling this off without an exception mechanism, but Rust is not the first to do so.
- I wonder what started it, per ML.

[Error Handling · OCaml Tutorials](https://ocaml.org/docs/error-handling)
> The Stdlib module contains the following type:
ocaml

```
type ('a, 'b) result =
  | Ok of 'a
  | Error of 'b
```



I let GPT4 explain it, and it's a long story, but it's useful, so I'll record it.
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>The Result type is an enumeration (enum) in the Rust programming language that can return the result of a successful operation or an error if it fails for any reason. It is used to make error handling safer and more effective.

The Result type is defined as follows
rust

```
enum Result<T, E> {
    Ok(T),
    Err(E),
}
```

where T represents the return type if the operation succeeds and E represents the error type.

examples showing the use (of a word)
For example, if a file opening operation may fail, it is common for the function to return a Result type. If the file was opened successfully, the Ok variant is used to return the file handle, and if an error occurred, the Err variant returns error information.

rust

```
use std::fs::File;

fn open_file(path: &str) -> Result<File, std::io::Error> {
    let file = File::open(path)?;
    Ok(file)
}
```

This function uses the ? operator. This operator performs an early return if Result is Err and returns the error as is. If Result is Ok, it extracts the value in Ok.

error handling
The main advantage of using the Result type is that errors must be handled explicitly. This ensures that errors are not ignored and are properly handled.

rust

```
fn process_file(path: &str) {
    match open_file(path) {
        Ok(file) => {
            // Processing if the file is opened successfully
            println!("File opened successfully!");
        },
        Err(e) => {
            // Processing in the event of an error
            println!("Failed to open file: {}", e);
        },
    }
}
```

Thus, utilizing the Result type improves program robustness and prevents unexpected behavior due to errors.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>There's something similar in Haskell.

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Yes, Haskell has a concept similar to the Result type, and that is the Either type, a generic data type for holding one of two values, typically used for error handling and other situations. This type is defined as follows

hs

```
data Either a b = Left a | Right b
```


Here, Left is usually used to represent an error or non-normal situation, and Right is used to represent a success or normal result; using the Either type allows a function to have several different failure modes and represent them appropriately.

Example of use in Haskell
Taking the file open operation as an example, we can use the Either type to handle errors as follows:

haskel

```
import System.IO
import System.IO.Error

tryOpenFile :: FilePath -> IO (Either IOError Handle)
tryOpenFile path = tryIOError (openFile path ReadMode)
```

This function returns an IOError wrapped in Left or a file handle wrapped in Right on success.

error handling
Error handling with the Either type in Haskell is done through pattern matching:

haskell

```
processFile :: FilePath -> IO ()
processFile path = do
    result <- tryOpenFile path
    case result of
        Left err -> putStrLn $ "Failed to open file: " ++ show err
        Right handle -> do
            putStrLn "File opened successfully!"
            hClose handle
```


In this example, a value of type Either returned from tryOpenFile is branched with a case expression. An error message is output in case of an error (Left) and a success message is output in case of success (Right) and the file is closed.

Thus, the Either type is a powerful tool for error handling and distinguishing between two other results in Haskell.

- [[Proposed Technical Additions to Support Coding]]

---
This page is auto-translated from [/nishio/Result型](https://scrapbox.io/nishio/Result型) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.