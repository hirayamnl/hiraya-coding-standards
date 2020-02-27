<h1 align="center">
Hiraya MNL Engineering Team Coding Standards
</h1>

This document is meant to serve as the complete guide of Hiraya MNL Engineering Team’s codebases, covering how the codes should be formatted as well as efficiently using version control. Our goal is to ensure a consistently high-quality codebase that is easy to read and contribute to, especially for newcomers.

You are not forced to religiously follow these standards. However, you are expected to at least meet the bare minimum.

## Table of Contents
1. [General](#general)
2. [String literals](#string-literals)
3. [PHP](#php)
    - [File conventions](#file-conventions)
    - [Naming conventions](#naming-conventions)
    - [Defining class](#defining-class)
    - [Defining properties](#defining-properties)
    - [Defining functions/methods](#defining-functionsmethods)
    - [Defining conditional statements](#defining-conditional-statements)
    - [Conditional statements comparison](#conditional-statements-comparison)
    - [Commenting/Documenting code](#commentingdocumenting-code)
    - [Laravel rules](#laravel-rules)
    - [Composer](#composer)
    - [Other PHP rules](#other-php-rules)
3. [JavaScript](#javascript)
    - [File conventions](#file-conventions-1)
    - [Naming conventions](#naming-conventions-1)
    - [Defining class](#defining-class-1)
    - [Defining functions/methods](#definingfunctions-methods-1)
    - [Defining conditional statements](#defining-conditional-statements-1)
    - [Conditional statements comparison](#conditional-statements-comparison-1)
    - [Commenting/Documenting code](#commentingdocumenting-code-1)
    - [VueJS rules](#vuejs-rules)
    - [NPM](#npm)
    - [Other JavaScript rules](#other-javascript-rules)
4. [CSS](#css)
5. [Git](#git)
    - [Workflow](#workflow)
    - [Branches](#branches)
    - [Naming conventions](#naming-conventions-2)
    - [Commits](#commits)
    - [Pull Requests](#pull-requests)
    - [Code Reviews](#code-reviews)
6. [Testing](#testing)
7. [License](#license)

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
- There must always be a `namespace` on each file.
- `namespace` must be written on two newlines after `<?php`

### Naming conventions
- Variables and function names should be written in camelCase format.
- Constants should be written in UPPER_SNAKE_CASE format.
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
- You must put a new line before `{` in function definitions.
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
```php
if ($condition == true) {
    // Code here...
}
...
if (
    $condition == true &&
    ($condition1 == $condition2) ||
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

### Commenting/Documenting code
- Single-line and multi-line comments must start with `/**` and end with `*/`.
- You must always include a comment on class variables.
- Refrain from commenting on a function if the function name already explains what the function is for, except for functions in `repository` interfaces.
- `Repository` interface functions must always have a comment on what the function is for.
- `Repository` class functions must not have any comments.
- You must always use `@var` for variable type comments.
- You must always use `@param` for parameter type in comments.
- You must always use `@return` for return type in comments.
- There must always be two whitespaces between `@param` and `data type`.
- There must always be a short description on each `@param` comments.
```php
class ClassName
{
    /** @var VariableType */
    public $classVariable;

    /**
     * This is the function description where you explain what
     * the function does.
     *
     * @param  Model $id the user's unique id
     * @param  array $otherData user's other data
     * @return Array
     */
    public function someFunction(Model $id, array $otherData): Array
    {
        // Code here...

        return $arrayType;
    }
}
```

### Laravel rules
- You must follow the [rules accepted by the Laravel community](https://github.com/alexeymezenin/laravel-best-practices).

### Composer
- When installing third-party packages, it should always be the latest version when available.
- Third-party packages in `composer.json` file must have a fixed version number to avoid breaking changes.
```json
{
    "require": {
        "vendor/package": "1.10.11"
    }
}
```

### Other PHP rules
- For rules that are not mentioned here, please refer to the [PSR-12 Coding Standards](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-12-extended-coding-style-guide.md)

## JavaScript
### File conventions
- It is recommended to use 2 spaces instead of tabs as indents.
- `import` of modules must always be at the top.
- `export` statements must always be at the bottom.
- You must omit `;` as it makes chaining easier and commit diffs cleaner.

### Naming conventions
- Variables and function names should be written in camelCase format.
- Constructors and class names should be written in PascalCase format.
- Acronyms should always be UPPERCASED.
- `is` or `has` prefix should be used when naming `boolean` type variables.
- `var` should not be used when defining variables, use `let` or `const` instead.

### Defining class
- `{` and `extend` keyword must be written on the same line as the class name.
```js
class ClassName extends BaseClass {
  // Code here

  return someVariable
}
```

### Defining function/methods 
- You must not put any spaces before `(` and after `)`.
- You must not put any whitespaces before commands in arguments, put them after instead.
- If there are too many arguements, you must put a new line after `(` and write one argument per line. You should also write `)` and `{` on the same line, separated by a whitespace.
```js
class ClassName {
  constructor(name, level) {
    this.name = name
    this.level = level
  }

  someFunction(
    name,
    level,
    status,
    otherData
  ) {
    // Code here

    return someData
  }
}
```

### Defining conditional statements
- You must not put newline before curly braces.
- You must put one space before `(` and after `)`.
- You must not put any whitespaces after `(` and before `)`.
- If there are too many arguments, you must put a newline after `(` and write one argument per line. You should also write `)` and `{` on the same line, seperated by a whitespace.
```js
if (condition == true) {
  // Code here...
}
...
if (
  condition == true &&
  (condition1 == condition2) ||
  condition3 != 'some condition here'
) {
  // Code here...
}
```

### Conditional statements comparison
- You must have the check target of the comparison on the right.
```js
if (condition == null) {
  // Code here...
}
```

### VueJS rules
- For VueJS style guide, please refer to [VueJS Style Guide](https://vuejs.org/v2/style-guide/)
- For VueJS best practices, please refer to [VueJS Best Practices](https://012.vuejs.org/guide/best-practices.html)

### NPM
- When installing third-party packages, it should always be the latest version when available.
- Third-party packages in `package.json` file must have a fixed version number to avoid breaking changes.
```json
{
    "dependencies": {
        "npm-package": "1.10.11"
    }
}
```

### Other JavaScript rules
- For rules that are not mentioned here, please refer to [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)

## CSS
- You are to follow [Airbnb CSS Style Guide](https://github.com/airbnb/css)

## Git
### Workflow
- The [Gitflow Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) must be strictly followed.
- While it's easier to use the `git-flow` library, it's recommended to use vanilla git instead.

### Branches
- The `master` branch is the default branch and is also a protected branch.
- The `develop` branch will contain the complete history of the project. This is also the parent branch of all `feature` branches.
- The `feature` branch will contain the code for each product feature. Each new product feature should reside in its own branch. When a feature is complete, it gets merge back into `develop` branch.
- The `hotfix` branch will be used to quickly patch critical bugs in production releases, it will branch-out of the `master` branch and be merged back into it and `develop` as soon as the fix is complete.
- The `release` branch will branch-out of the `develop` branch once it has acquired enough features for a release. Once it's ready to ship, it will merge into `master` and tagged with a version number and should also be merged back into `develop` if changes occured since the release was initiated.
- `feature`, `hotfix`, and `release` branches must be deleted right after they are merged to reduce clutter.

### Naming conventions
- `feature` branches should be have a prefix of `feature/`.
- `hotfix` branches should have a prefix of `hotfix/`.
- `release` branches should have a prefix of `release/`.
- `Alpha` and `Beta` releases must have a prefix of `alpha_` and `beta_`.
- All versions must have a prefix of `v` (i.e v1.0.1).
```sh
git checkout -b feature/feature-name
git checkout -b hotfix/hotfix-name
git checkout -b release/beta_v1.0.1
```

### Commits
- Commit messages should briefly explain what the changes are.
- You must follow the "commit small, commit often" practice which makes it easier for everyone to integrate changes regularly and avoid massive merge conflicts.
- Do not commit half-done work, specially if it's a breaking change.

### Pull Requests
- Pull Request titles should briefly explain what the PR is for.
- Pull Request descriptions should include a list of changes included in the PR and other relevant information.
- You must update your branch and fix merge conflicts on your local machine before creating a Pull Request.

### Code Reviews
- Code review is a must, before every pull request is accepted.
- Code review must be requested to the Engineering Lead or CTO.
- During code review, there will be checks including but is not limited to:
    - Formatting and architecture
    - Reusability and reliability
    - Scalability and performance
    - Security and documentation

## Testing
- TODO

### License
MIT License

Copyright (c) 2020 Hiraya MNL

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
