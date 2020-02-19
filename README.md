<h1 align="center">
Hiraya MNL Engineering Team Coding Standards
</h1>
This document is meant to serve as the complete guide of Hiraya MNL Engineering Team’s codebases, covering how the codes should be formatted as well as efficiently using version control. Our goal is to ensure a consistently high-quality codebase that is easy to read and contribute to, especially for newcomers.

You are not forced to religiously follow these standards. However, you are expected to at least meet the bare minimum.

## General
- There is no hard limit for line length but the general rule of tab should be less than 120 characters (this is also the limit for Github code review).
- There should always be a newline at the end of the file.
- You must put a trailing comma on the last element of an array.
- Single responsibility principle must be followed.
- There should always be a newline before the `return` statement.

## String literals
- While it is recommended to use single-quote, be consistent when picking either single-quote or double-quote and stick with it. It is okay to use the other quote on a string to avoid the need to double-backslash escape within the string. 

## PHP
### File conventions
- It is recommended to use 4 spaces instead of tabs as indents.
- Files must start with `<?php` and you must omit `?>` at the end of file. 

### Naming conventions
- Variables and function names should be written in camelCase format.
- Constant and class variables should be written in UPPER_SNAKE_CASE format.
- Class names should be written in PascalCase.

### Defining class
- You must put a newline before `{` in class definitions. Also `extends` and `implements` must be written on the same line as the class name.
- The `abstract`/`final`/`trait` keywords must come before class definition.
- You must add an `Abstract` prefix to an abstract class name.
- You must add an `Interface` suffix to an interface class name.
- You must add a `Trait` suffix to a trait name.
```php
class ClassName extends AnotherClassName implements Interface
{
	// Code here...

	return $someStuffs;
}
...
abstract class AbstractClassName
{
	// Code here...

	return $something;
}
...
interface ClassNameInterface
{
	// Code here...
}
...
trait SomeTrait
{
	// Code here...
}
```

### Defining properties
- You must not omit `public`/`private`/`protected` modifiers.
- You should always explicitly write `public` as the default modifier.
- The `static` keyword must come after the modifiers.
- You must not use `var` when defining properties because you can't add modifiers.
- You must not define two or more properties in one statement.
```php
class ClassName
{
	public $propertyOne;
	private $propertyTwo;
	protected static $staticProperty;
}
```

### Defining functions/methods
- You must not omit `public`/`private`/`protected` modifiers.
- You should always explicitly write `public` as the default modifier.
- The `abstract`/`final` keywords must come before the modifiers.
- You must not put any spaces before `(` and after `)`.
- You must not put any whitespaces before commands in arguments, put them after instead.
- You must always use type hinting on arguments to specify the expected data type.
- When possible, you must declare the return type of a function/method.
- If there are too many arguments, you must put a newline after `(` and write one argument per line. You should also write `)` and `{` on the same line, seperated by a whitespace.
```php
class ClassName
{
	abstract protected function doSomething(array $data): Array
	{
		// Code here...

		return $array;
	}

	public function somethingWasDone(string $status, int $code): Class
	{
		// Code here...

		return $classInstance;
	}

	public function tooMany(
		string $name,
		int $status,
		array $otherData
	) {
		// Code here...
	}
}
```

### Defining conditional statements
- You must not put newline before curly braces.
- You must put one space before `(` and after `)`.
- You must not put any whitespaces after `(` and before `)`.
- If there are too many arguments, you must put a newline after `(` and write one argument per line. You should also write `)` and `{` on the same line, seperated by a whitespace.
- If there are too many arguments, you must put a newline after `(` and write one argument per line. You should also write `)` and `{` on the same line, seperated by a whitespace.
```php
if ($condition == true) {
	// Code here...
}
...
if (
	$condition == true &&
	($condition1 == $condition 2) ||
	$condition3 != 'some condition here'
) {
	// Code here...
}
```

### Conditional statements comparison
- You must have the check target of the comparison on the right.
```php

if ($condition == null) {
	// Code here...
}
```
### Laravel rules
- You must follow the [rules accepted by the Laravel community](https://github.com/alexeymezenin/laravel-best-practices).

### Other PHP rules
- For rules that are not mentioned here, please refer to the [PSR-12 Coding Standards](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-12-extended-coding-style-guide.md)

## JavaScript
- You are to follow [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)

## CSS
- You are to follow [Airbnb CSS Style Guide](https://github.com/airbnb/css)

## Git
- TODO

## Testing
- TODO
