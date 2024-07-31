# PHP 8.1 Changes

## New Features
* **Enums:**
  * Definition: Strongly typed enumerations.
  * Syntax:
    ```php
    enum Suit: string {
        case Hearts = 'H';
        case Diamonds = 'D';
        case Clubs = 'C';
        case Spades = 'S';
    }
    ```
  * Benefits: Improved type safety, code readability.
* **Fibers:**
  * Definition: Cooperative multitasking for asynchronous programming.
  * Syntax:
    ```php
    $fiber = new Fiber(function() {
        // Fiber code
    });
    $fiber->start();
    ```
  * Benefits: Non-blocking operations, better performance.
* **...** (other new features)

## Improved Features
* **Type System:**
  * Enhanced type inference, union types, intersection types.
  * Example:
    ```php
    function processData(mixed $data): void {
        // ...
    }
    ```
* **...** (other improved features)

## Backward Incompatible Changes
* **Default Error Mode for MySQLi:**
  * Changed to exceptions.
  * Implications: Modify error handling code.
* **...** (other backward incompatible changes)

## Deprecations
* **Filter Functions:**
  * `FILTER_SANITIZE_STRING` and `FILTER_SANITIZE_STRIPPED` are deprecated.
  * Alternatives: Use alternative sanitization methods.
* **...** (other deprecations)

## Performance Improvements
* JIT compiler for ARM64.
* Inheritance cache.
* Fast class name resolution.
* ...

## Other Changes
* HTML encoding and decoding functions now use ENT_QUOTES | ENT_SUBSTITUTE.
* Customizable line endings for CSV writing functions.
* ...
