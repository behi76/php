<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PHP 8.1 Changes</title>
</head>
<body>
    <h1>PHP 8.1 Changes</h1>

    <h2>New Features</h2>

    <h3>1. Enums</h3>
    <p>PHP 8.1 introduces Enumerations, a way to define a set of possible values for a variable. Enums are backed by a scalar type.</p>
    <pre><code>enum Status: string {
    case PENDING = 'pending';
    case APPROVED = 'approved';
    case REJECTED = 'rejected';
}
    </code></pre>

    <h3>2. Readonly Properties</h3>
    <p>Properties can now be marked as <code>readonly</code>, making them immutable after initialization.</p>
    <pre><code>class User {
    public readonly string $name;

    public function __construct(string $name) {
        $this->name = $name;
    }
}
    </code></pre>

    <h3>3. Fibers</h3>
    <p>Fibers are primitives for implementing lightweight concurrency. They allow functions to be paused and resumed.</p>
    <pre><code>$fiber = new Fiber(function(): void {
    $value = Fiber::suspend('fiber');
    echo "Value: $value\n";
});

$value = $fiber->start();
$fiber->resume('main');
    </code></pre>

    <h3>4. Intersection Types</h3>
    <p>Intersection types are now supported, allowing a variable to be constrained to multiple types simultaneously.</p>
    <pre><code>function process(ServerRequestInterface&amp;RequestHandlerInterface $request): void {
    // Implementation
}
    </code></pre>

    <h3>5. <code>never</code> Return Type</h3>
    <p>The <code>never</code> return type is used to indicate that a function does not return any value and always terminates with an exception or error.</p>
    <pre><code>function redirect(string $url): never {
    header("Location: " . $url);
    exit;
}
    </code></pre>

    <h3>6. Array Unpacking with String Keys</h3>
    <p>Array unpacking is now possible with string keys.</p>
    <pre><code>$array1 = ["a" => 1, "b" => 2];
$array2 = ["c" => 3, ...$array1];

print_r($array2);
// Output: ["c" => 3, "a" => 1, "b" => 2]
    </code></pre>

    <h2>Deprecated Features and Changes</h2>

    <h3>1. <code>match</code> with non-exhaustive values</h3>
    <p>In PHP 8.1, using <code>match</code> expressions with non-exhaustive values will result in a compile-time error.</p>
    <pre><code>$condition = 1;
$result = match($condition) {
    1 => 'one',
    2 => 'two',
    // No default case, will cause an error if $condition is not 1 or 2.
};
    </code></pre>

    <h3>2. <code>str_starts_with()</code> and <code>str_ends_with()</code></h3>
    <p>These new functions check if a string starts or ends with a given substring.</p>
    <pre><code>if (str_starts_with('Hello, world!', 'Hello')) {
    echo "The string starts with 'Hello'.";
}

if (str_ends_with('Hello, world!', 'world!')) {
    echo "The string ends with 'world!'.";
}
    </code></pre>

</body>
</html>
