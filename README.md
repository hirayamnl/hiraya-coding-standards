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
4. [Swift](#swift)
    - [Correctness](#correctness)
    - [Naming conventions](#naming-conventions-1)
    - [Language](#language)
    - [Defining class](#defining-class-1)
    - [Defining functions](#defining-functions-1)
    - [Defining conditional statements](#defining-conditional-statements-1)
    - [Conditional statements](#conditional-statements-1)
    - [Optionals](#optionals-1)
    - [Code Organization](#code-organization-1)
    - [Protocol Conformance](#protocol-conformance-1)
    - [Spacing](#spacing-1)
    - [Other Swift Rules](#other-swift-rules-1)
5. [CSS](#css)
6. [Git](#git)
    - [Workflow](#workflow)
    - [Branches](#branches)
    - [Naming conventions](#naming-conventions-2)
    - [Commits](#commits)
    - [Pull Requests](#pull-requests)
    - [Code Reviews](#code-reviews)
7. [Testing](#testing)
8. [License](#license)
9. [Amendments](#amendments)

## General
- There is no hard limit for line length but the general rule of tab should be less than 120 characters (this is also the limit for Github code review).
- There should always be a newline at the end of the file.
- You must put a trailing comma on the last element of an array.
- Single responsibility principle must be followed.
- There should always be a newline before the `return` statement.

**[⬆ back to top](#table-of-contents)**

## String literals
- While it is recommended to use single-quote, be consistent when picking either single-quote or double-quote and stick with it. It is okay to use the other quote on a string to avoid the need to double-backslash escape within the string.

**[⬆ back to top](#table-of-contents)**

## PHP
### File conventions
- It is recommended to use 4 spaces instead of tabs as indents.
- Files must start with `<?php` and you must omit `?>` at the end of file.
- There must always be a `namespace` on each file.
- `namespace` must be written on two newlines after `<?php`.

**[⬆ back to top](#table-of-contents)**

### Naming conventions
- Variables, function names and parameters should be written in camelCase format.
- Constants should be written in UPPER_SNAKE_CASE format.
- Class names should be written in PascalCase.

**[⬆ back to top](#table-of-contents)**

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

**[⬆ back to top](#table-of-contents)**

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

**[⬆ back to top](#table-of-contents)**

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

**[⬆ back to top](#table-of-contents)**

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

**[⬆ back to top](#table-of-contents)**

### Conditional statements comparison
- You must have the check target of the comparison on the right.
```php

if ($condition == null) {
    // Code here...
}
```

**[⬆ back to top](#table-of-contents)**

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

**[⬆ back to top](#table-of-contents)**

### Laravel rules
- You must follow the [rules accepted by the Laravel community](https://github.com/alexeymezenin/laravel-best-practices).

**[⬆ back to top](#table-of-contents)**

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

**[⬆ back to top](#table-of-contents)**

### Other PHP rules
- For rules that are not mentioned here, please refer to the [PSR-12 Coding Standards](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-12-extended-coding-style-guide.md)

**[⬆ back to top](#table-of-contents)**

## JavaScript
### File conventions
- It is recommended to use 2 spaces instead of tabs as indents.
- `import` of modules must always be at the top.
- `export` statements must always be at the bottom.
- You must omit `;` as it makes chaining easier and commit diffs cleaner.

**[⬆ back to top](#table-of-contents)**

### Naming conventions
- Variables, function names and parameters should be written in camelCase format.
- Constructors and class names should be written in PascalCase format.
- Acronyms should always be UPPERCASED.
- `is` or `has` prefix should be used when naming `boolean` type variables.
- `var` should not be used when defining variables, use `let` or `const` instead.

**[⬆ back to top](#table-of-contents)**

### Defining class
- `{` and `extend` keyword must be written on the same line as the class name.
```js
class ClassName extends BaseClass {
  // Code here

  return someVariable
}
```

**[⬆ back to top](#table-of-contents)**

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

**[⬆ back to top](#table-of-contents)**

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

**[⬆ back to top](#table-of-contents)**

### Conditional statements comparison
- You must have the check target of the comparison on the right.
```js
if (condition == null) {
  // Code here...
}
```

**[⬆ back to top](#table-of-contents)**

### Commenting/Documenting code
- Comments with `//` are allowed, however it is recommended to use `/** */` for single-line and multi-line comments instead.
- Refrain from commenting on a function if the function name already explains what the function is for.
- Refrain from commenting on client-side JS as this helps with code obfuscation.
- You must always use `@param` for parameter type in comments.
- You must always use `@return` for return type in comments.
- There must always be two whitespaces between `@param` and `data type`.
- `data type` in `@param` and `@return` comments must be enclosed in `{}`, you must not put any whitespace after `{` and before `}`
- There must always be a short descrption on each `@param` comments.
```js
class ClassName {
  /**
   * This is the recommended way to document/comment
   * javascript codes.
   *
   * @param  {String} name the user's first name
   * @param  {Number} level the user's current level
   * @param  {Boolean} status the user's account status
   * @return {Array}
   */
  someFunction(name, level, status) {
    // Code here...
  }
}
...
// This comment is allowed too, but the first one just
// look more prettier :).
//
// @param  {Number} id unique id of the item
// @param  {Array} moreData other necessary data of the item
// @return {Array}
let anotherFunction = function(id, moreData) {
  // Code here...
}
```

**[⬆ back to top](#table-of-contents)**

### VueJS rules
- For VueJS style guide, please refer to [VueJS Style Guide](https://vuejs.org/v2/style-guide/)
- For VueJS best practices, please refer to [VueJS Best Practices](https://012.vuejs.org/guide/best-practices.html)

**[⬆ back to top](#table-of-contents)**

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

**[⬆ back to top](#table-of-contents)**

### Other JavaScript rules
- For rules that are not mentioned here, please refer to [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)

**[⬆ back to top](#table-of-contents)**

## Swift

- These standards apply to Swift 5.0 and later.
- When using Swift, use Swift 5.0 or higher.
- Favor readability and clarity above fewer keystrokes.

### Correctness
- Strive to make your code compile without warnings. This rule informs many style decisions such as using #selector types instead of string literals.

**Preferred**:
```swift
NotificationCenter.default.addObserver(self, selector: "updateResult:", name: "updateResult", object: nil)
```

**Not Preferred**:
```swift
NotificationCenter.default.addObserver(self, selector: #selector(InterfaceController.updateResult(_:)), name: "updateResult", object: nil)
}

```

### Naming conventions
- Use the Swift naming conventions described in the API Design Guidelines. Some key takeaways include:
    - using camelCase (not snake_case)
    - using UpperCamelCase for types and protocols, lowerCamelCase for everything else
    - using terms that don't surprise experts or confuse beginners
    - choosing good parameter names that serve as documentation
```swift
protocol UserDelegate { 
}

class User { 
    let firstName
    let lastName
}
```
### Language 
- Use US English spelling to match Apple's API.

**Preferred**:
```swift
let color = "red"
```

**Not Preferred**:
```swift
let colour = "red"
}

```

### Defining class

- Remember, structs have [value semantics](https://developer.apple.com/library/mac/documentation/Swift/Conceptual/Swift_Programming_Language/ClassesAndStructures.html#//apple_ref/doc/uid/TP40014097-CH13-XID_144). Use structs for things that do not have an identity. An array that contains [a, b, c] is really the same as another array that contains [a, b, c] and they are completely interchangeable. It doesn't matter whether you use the first array or the second, because they represent the exact same thing. That's why arrays are structs.

- Classes have [reference semantics](https://developer.apple.com/library/mac/documentation/Swift/Conceptual/Swift_Programming_Language/ClassesAndStructures.html#//apple_ref/doc/uid/TP40014097-CH13-XID_145). Use classes for things that do have an identity or a specific life cycle. You would model a person as a class because two person objects are two different things. Just because two people have the same name and birthdate, doesn't mean they are the same person. But the person's birthdate would be a struct because a date of 3 March 1950 is the same as any other date object for 3 March 1950. The date itself doesn't have an identity.

- Sometimes, things should be structs but need to conform to `AnyObject` or are historically modeled as classes already (`NSDate`, `NSSet`). Try to follow these guidelines as closely as possible.

### Example definition

Here's an example of a well-styled class definition:

```swift
class Circle: Shape {
  var x: Int, y: Int
  var radius: Double
  var diameter: Double {
    get {
      return radius * 2
    }
    set {
      radius = newValue / 2
    }
  }

  init(x: Int, y: Int, radius: Double) {
    self.x = x
    self.y = y
    self.radius = radius
  }

  convenience init(x: Int, y: Int, diameter: Double) {
    self.init(x: x, y: y, radius: diameter / 2)
  }

  override func area() -> Double {
    return Double.pi * radius * radius
  }
}

extension Circle: CustomStringConvertible {
  var description: String {
    return "center = \(centerString) area = \(area())"
  }
  private var centerString: String {
    return "(\(x),\(y))"
  }
}
```

The example above demonstrates the following style guidelines:

 + Specify types for properties, variables, constants, argument declarations and other statements with a space after the colon but not before, e.g. `x: Int`, and `Circle: Shape`.
 + Define multiple variables and structures on a single line if they share a common purpose / context.
 + Indent getter and setter definitions and property observers.
 + Don't add modifiers such as `internal` when they're already the default. Similarly, don't repeat the access modifier when overriding a method.
 + Organize extra functionality (e.g. printing) in extensions.
 + Hide non-shared, implementation details such as `centerString` inside the extension using `private` access control.

### Defining functions
- You must add the opening curly brace inline of the function name
- Do not add public, becasue public is the default type of a function.
- You must add private when you want the method to be accessed only inside of the class

```swift
class User
{
    func isValidEmail(email: String) -> Bool {
        // Code here...
        var bool: Bool = true
        return bool;
    }

    private func isValidEmail(email: String) -> Bool {
        // Code here...
        var bool: Bool = true
        return bool;
    }
}
```

### Defining conditional statements
- You must add the opening curly brace inline of the function name
- You must put one space before conditional statement`.
- If you're comparing a boolean property you must not use "== true" statement

**Preferred**:
```swift
var emailIsValid: Bool = true

if emailIsValid { 

}
```

**Not Preferred**:
```swift
var emailIsValid: Bool = true

if emailIsValid == true {

}

```

### Conditional statements
- Use the enumerated() function if you need to loop over a Sequence and use the index:
```swift
for (index, element) in someArray.enumerated() {
    ...
}

```
- Use map when transforming Arrays (compactMap for Arrays of Optionals or flatMap for Arrays of Arrays):
```swift
let array = [1, 2, 3, 4, 5]
let stringArray = array.map { item in
    return "item \(item)"
}

let optionalArray: [Int?] = [1, nil, 3, 4, nil]
let nonOptionalArray = optionalArray.compactMap { item -> Int? in
    guard let item = item else {
        return nil
    }

    return item * 2
}

let arrayOfArrays = [array, nonOptionalArray]
let anotherStringArray = arrayOfArrays.flatmap { item in
    return "thing \(item)"
}
```
- If you are not performing a transform, or if there are side effects do not use map/flatmap; use a for in loop instead (tips).

- Avoid the use of forEach except for simple one line closures, similar to makeObjectsPerformSelector: in Objective-C.

### Optionals

- Declare variables and function return types as optional with `?` where a `nil` value is acceptable.

- Use implicitly unwrapped types declared with `!` only for instance variables that you know will be initialized later before use, such as subviews that will be set up in `viewDidLoad()`. Prefer optional binding to implicitly unwrapped optionals in most other cases.

- When accessing an optional value, use optional chaining if the value is only accessed once or if there are many optionals in the chain:

```swift
textContainer?.textLabel?.setNeedsDisplay()
```

- Use optional binding when it's more convenient to unwrap once and perform multiple operations:

```swift
if let textContainer = textContainer {
  // do many things with textContainer
}
```

- When naming optional variables and properties, avoid naming them like `optionalString` or `maybeView` since their optional-ness is already in the type declaration.

- For optional binding, shadow the original name whenever possible rather than using names like `unwrappedView` or `actualLabel`.

**Preferred**:
```swift
var subview: UIView?
var volume: Double?

// later on...
if let subview = subview, let volume = volume {
  // do something with unwrapped subview and volume
}

// another example
resource.request().onComplete { [weak self] response in
  guard let self = self else { return }
  let model = self.updateModel(response)
  self.updateUI(model)
}
```

**Not Preferred**:
```swift
var optionalSubview: UIView?
var volume: Double?

if let unwrappedSubview = optionalSubview {
  if let realVolume = volume {
    // do something with unwrappedSubview and realVolume
  }
}

// another example
UIView.animate(withDuration: 2.0) { [weak self] in
  guard let strongSelf = self else { return }
  strongSelf.alpha = 1.0
}
```

### Code Organization
- Use extensions to organize your code into logical blocks of functionality. Each extension should be set off with a // MARK: - comment to keep things well-organized.

### Protocol Conformance
* In particular, when adding protocol conformance to a model, prefer adding a separate extension for the protocol methods. This keeps the related methods grouped together with the protocol and can simplify instructions to add a protocol to a class with its associated methods.

**Preferred**:
```swift

class MyViewController: UIViewController {
  // class stuff here
}

// MARK: - UITableViewDataSource
extension MyViewController: UITableViewDataSource {
  // table view data source methods
}

// MARK: - UIScrollViewDelegate
extension MyViewController: UIScrollViewDelegate {
  // scroll view delegate methods
}
```

**Not Preferred**:
```swift

class MyViewController: UIViewController, UITableViewDataSource, UIScrollViewDelegate {
  // all methods
}

```
* Since the compiler does not allow you to re-declare protocol conformance in a derived class, it is not always required to replicate the extension groups of the base class. This is especially true if the derived class is a terminal class and a small number of methods are being overridden. When to preserve the extension groups is left to the discretion of the author.

* For UIKit view controllers, consider grouping lifecycle, custom accessors, and IBAction in separate class extensions.

### Spacing

* Indent using 2 spaces rather than tabs to conserve space and help prevent line wrapping. Be sure to set this preference in Xcode and in the Project settings as shown below:

![Xcode indent settings](screens/indentation.png)

* Method braces and other braces (`if`/`else`/`switch`/`while` etc.) always open on the same line as the statement but close on a new line.

**Preferred**:
```swift
class TestDatabase: Database {

  var data: [String: CGFloat] = ["A": 1.2, "B": 3.2]
  
}
```

**Not Preferred**:
```swift
class TestDatabase : Database {

  var data :[String:CGFloat] = ["A" : 1.2, "B":3.2]
  
}
```
* There should be one blank line between methods and up to one blank line between type declarations to aid in visual clarity and organization. Whitespace within methods should separate functionality, but having too many sections in a method often means you should refactor into several methods.

* There should be one blank lines after an opening brace or before a closing brace.

### Other Swift Rules
* [RaywenderLich](https://github.com/raywenderlich/swift-style-guide/blob/master/README.markdown)
* [The Swift Programming Language](https://developer.apple.com/library/prerelease/ios/documentation/swift/conceptual/swift_programming_language/index.html)
* [Swift Standard Library Reference](https://developer.apple.com/library/prerelease/ios/documentation/General/Reference/SwiftStandardLibraryReference/index.html)

**[⬆ back to top](#table-of-contents)**

## CSS
- You are to follow [Airbnb CSS Style Guide](https://github.com/airbnb/css)

**[⬆ back to top](#table-of-contents)**

## Git
### Workflow
- The [Gitflow Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) must be strictly followed.
- While it's easier to use the `git-flow` library, it's recommended to use vanilla git instead.

**[⬆ back to top](#table-of-contents)**

### Branches
- The `master` branch is the default branch and is also a protected branch.
- The `develop` branch will contain the complete history of the project. This is also the parent branch of all `feature` branches.
- The `feature` branch will contain the code for each product feature. Each new product feature should reside in its own branch. When a feature is complete, it gets merge back into `develop` branch.
- The `hotfix` branch will be used to quickly patch critical bugs in production releases, it will branch-out of the `master` branch and be merged back into it and `develop` as soon as the fix is complete.
- The `release` branch will branch-out of the `develop` branch once it has acquired enough features for a release. Once it's ready to ship, it will merge into `master` and tagged with a version number and should also be merged back into `develop` if changes occured since the release was initiated.
- `feature`, `hotfix`, and `release` branches must be deleted right after they are merged to reduce clutter.

**[⬆ back to top](#table-of-contents)**

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

**[⬆ back to top](#table-of-contents)**

### Commits
- Commit messages should briefly explain what the changes are.
- You must follow the "commit small, commit often" practice which makes it easier for everyone to integrate changes regularly and avoid massive merge conflicts.
- Do not commit half-done work, specially if it's a breaking change.

**[⬆ back to top](#table-of-contents)**

### Pull Requests
- Pull Request titles should briefly explain what the PR is for.
- Pull Request descriptions should include a list of changes included in the PR and other relevant information.
- You must update your branch and fix merge conflicts on your local machine before creating a Pull Request.

**[⬆ back to top](#table-of-contents)**

### Code Reviews
- Code review is a must, before every pull request is accepted.
- Code review must be requested to the Engineering Lead or CTO.
- During code review, there will be checks including but is not limited to:
    - Formatting and architecture
    - Reusability and reliability
    - Scalability and performance
    - Security and documentation

**[⬆ back to top](#table-of-contents)**

## Testing
- TODO

**[⬆ back to top](#table-of-contents)**

### License
MIT License

**Copyright (c) 2020 Hiraya MNL**

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

**[⬆ back to top](#table-of-contents)**

### Amendments
We always try to keep our standards high, so if you noticed any errors in this guide such as typos, broken links, etc... or if you have an idea or a suggestion that would make this guide better, feel free to create a pull request with your changes.

**[⬆ back to top](#table-of-contents)**

