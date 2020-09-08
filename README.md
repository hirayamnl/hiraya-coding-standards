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
    - [Naming conventions](#naming-conventions-2)
    - [Language](#language)
    - [Defining class](#defining-class-2)
    - [Defining functions](#defining-functions-1)
    - [Defining conditional statements](#defining-conditional-statements-1)
    - [Conditional statements](#conditional-statements-1)
    - [Optionals](#optionals-1)
    - [Code Organization](#code-organization-1)
    - [Protocol Conformance](#protocol-conformance-1)
    - [Spacing](#spacing-1)
    - [Other Swift Rules](#other-swift-rules-1)
5.  [Android Kotlin](#android-kotlin)
    - [Source file](#source-file)
        + [Naming](#naming)
        + [Special Characters](#special-characters)
        + [Structure](#structure)
    - [Formatting](#formatting)
        + [Braces](#braces)
        + [Whitespace](#whitespace)
        + [Specific constructs](#specific-constructs)
        + [Naming](#naming-1)
        + [Documentation](#documentation)
6.  [CSS](#css)
7.  [Git](#git)
    -  [Workflow](#workflow)
    -  [Branches](#branches)
    -  [Naming conventions](#naming-conventions-3)
    -  [Commits](#commits)
    -  [Pull Requests](#pull-requests)
    -  [Code Reviews](#code-reviews)
7.  [Testing](#testing)
8.  [License](#license)
9.  [Amendments](#amendments)

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

#### Example definition

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
- You must put one space before conditional statement.
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

## Android Kotlin

This serves as the complete definition of Google’s Android coding standards for source code in the Kotlin Programming Language. A Kotlin source file is described as being in Google Android Style if and only if it adheres to the rules herein.

  

**[⬆ back to top](#table-of-contents)**

### Source file

All source files must be encoded as UTF-8.

  

**[⬆ back to top](#table-of-contents)**

- #### Naming
	
	If a source file contains only a single top-level class, the file name should reflect the case-sensitive name plus the `.kt` extension. Otherwise, if a source file contains multiple top-level declarations, choose a name that describes the contents of the file, apply PascalCase, and append the `.kt` extension.
	```kotlin
		// MyClass.kt
		class MyClass { }
	```
	```kotlin
		// Bar.kt
		class Bar { }
		fun Runnable.toBar(): Bar = // …
	```
	```kotlin
		// Map.kt
		fun <T, O> Set<T>.map(func: (T) -> O): List<O> = // …
		fun <T, O> List<T>.map(func: (T) -> O): List<O> = // …
	```
	
**[⬆ back to top](#table-of-contents)**

- #### Special Characters

	##### Whitespace characters

	Aside from the line terminator sequence, the  **ASCII horizontal space character (0x20)**  is the only whitespace character that appears anywhere in a source file. This implies that:

	- All other whitespace characters in string and character literals are escaped.
	- Tab characters are  _not_  used for indentation.
	 
	##### Special escape sequences

	For any character that has a special escape sequence (`\b`,  `\n`,  `\r`,  `\t`,  `\'`,  `\"`,  `\\`, and  `\$`), that sequence is used rather than the corresponding Unicode (e.g.,  `\u000a`) escape.

	##### Non-ASCII characters

	For the remaining non-ASCII characters, either the actual Unicode character (e.g.,  `∞`) or the equivalent Unicode escape (e.g.,  `\u221e`) is used. The choice depends only on which makes the code  **easier to read and understand.**  Unicode escapes are discouraged for printable characters at any location and are strongly discouraged outside of string literals and comments.

	| **Example** | **Discussion** |
	|--|--|
	| val unitAbbrev = "μs" | Best: perfectly clear even without a comment. |
	| val unitAbbrev = "\u03bcs" // μs | Poor: there’s no reason to use an escape with a printable character. |
	| val unitAbbrev = "\u03bcs"` | Poor: the reader has no idea what this is. |
	| return "\ufeff" + content | Good: use escapes for non-printable characters, and comment if necessary. |

**[⬆ back to top](#table-of-contents)**

- #### Structure
	
	A `.kt` file comprises the following, in order:
	-   Copyright and/or license header (optional)
	-   File-level annotations
	-   Package statement
	-   Import statements
	-   Top-level declarations

	Exactly one blank line separates each of these sections.

	##### Copyright / License
	
	If a copyright or license header belongs in the file it should be placed at the immediate top in a multi-line comment.
	```kotlin
		/*  
		 * Copyright 2017 Google, Inc.  
		 *  
		 * ...  
		 */
	```
	Do not use a [KDoc-style](https://kotlinlang.org/docs/reference/kotlin-doc.html) or single-line-style comment.
	```kotlin
		/**  
		 * Copyright 2017 Google, Inc.  
		 *  
		 * ...  
		 */
	```
	```kotlin
		// Copyright 2017 Google, Inc.  
		//  
		// ...
	```

	##### File-level annotations
	
	Annotations with the "file"  [use-site target](https://kotlinlang.org/docs/reference/annotations.html#annotation-use-site-targets)  are placed between any header comment and the package declaration.

	##### Package statement
	
	Annotations with the "file"  [use-site target](https://kotlinlang.org/docs/reference/annotations.html#annotation-use-site-targets)  are placed between any header comment and the package declaration.

	##### Import statements
	
	Import statements for classes, functions, and properties are grouped together in a single list and ASCII sorted.

	Wildcard imports (of any type) are  **not allowed.**

	Similar to the package statement, import statements are not subject to a column limit and they are never line-wrapped.

	##### Top-level declarations
	
	A  `.kt`  file can declare one or more types, functions, properties, or type aliases at the top-level.

	The contents of a file should be focused on a single theme. Examples of this would be a single public type or a set of extension functions performing the same operation on multiple receiver types. Unrelated declarations should be separated into their own files and public declarations within a single file should be minimized.

	No explicit restriction is placed on the number nor order of the contents of a file.

	Source files are usually read from top-to-bottom meaning that the order, in general, should reflect that the declarations higher up will inform understanding of those farther down. Different files may choose to order their contents differently. Similarly, one file may contain 100 properties, another 10 functions, and yet another a single class.

	What is important is that each class uses  **some**  logical order, which its maintainer could explain if asked. For example, new functions are not just habitually added to the end of the class, as that would yield “chronological by date added” ordering, which is not a logical ordering.

	##### Class member ordering
	
	The order of members within a class follow the same rules as the top-level declarations.

**[⬆ back to top](#table-of-contents)**

### Formatting

**[⬆ back to top](#table-of-contents)**

- #### Braces
	
	Braces are not required for `when` branches and `if` statement bodies which have no `else if/else` branches and which fit on a single line.

	```kotlin
		if (string.isEmpty()) return  
		  
		when (value) {  
			0 -> return  
			// …  
		}
	```

	Braces are otherwise required for any `if`, `for`, `when` branch, `do`, and `while` statements, even when the body is empty or contains only a single statement.

	```kotlin
		if (string.isEmpty())
			return // WRONG!

		if (string.isEmpty()) {
			return // Okay
		}
	```

	##### Non-empty blocks
	
	Braces follow the Kernighan and Ritchie style ("Egyptian brackets") for nonempty blocks and block-like constructs:

	-   No line break before the opening brace.
	-   Line break after the opening brace.
	-   Line break before the closing brace.
	-   Line break after the closing brace,  _only if_  that brace terminates a statement or terminates the body of a function, constructor, or  _named_  class. For example, there is  _no_  line break after the brace if it is followed by  `else`  or a comma.

	```kotlin
		return Runnable {
			while (condition()) {
				foo()  
			}
		}
	  
		return object : MyClass() {
			override fun foo() {
				if (condition()) {
					try {
						something()
					} catch (e: ProblemException) {
						recover()
					}
				} else if (otherCondition()) {
					somethingElse()
				} else { 
					lastThing()
				}
			}
		}
	```

	A few exceptions for [enum classes](#enum-classes) are given below.

	##### Empty blocks
	
	An empty block or block-like construct must be in K&R style.

	```kotlin
		try {
			doSomething()  
		} catch (e: Exception) {} // WRONG!
	```
	```kotlin
		try {
			doSomething()  
		} catch (e: Exception) {  
		} // Okay
	```

	##### Expressions
	
	An `if/else` conditional that is used as an expression may omit braces _only_ if the entire expression fits on one line.

	```kotlin
		val value = if (string.isEmpty()) 0 else 1 // Okay
	```
	```kotlin
		val value = if (string.isEmpty()) // WRONG!
			0  
		else
			1
	```
	```kotlin
		val value = if (string.isEmpty()) { // Okay
			0  
		} else {
			1  
		}
	```

	##### Indentation
	
	Each time a new block or block-like construct is opened, the indent increases by four spaces. When the block ends, the indent returns to the previous indent level. The indent level applies to both code and comments throughout the block.

	##### One statement per line
	
	Each statement is followed by a line break. Semicolons are not used.

	##### Line wrapping
	
	Code has a column limit of 100 characters. Except as noted below, any line that would exceed this limit must be line-wrapped, as explained below.

	Exceptions:

	-   Lines where obeying the column limit is not possible (for example, a long URL in KDoc)
	-   `package`  and  `import`  statements
	-   Command lines in a comment that may be cut-and-pasted into a shell

	##### Where to break
	
	The prime directive of line-wrapping is: prefer to break at a higher syntactic level. Also:
	
	-   When a line is broken at an operator or infix function name, the break comes after the operator or infix function name.
	-   When a line is broken at the following “operator-like” symbols, the break comes before the symbol:
	    -   The dot separator (`.`,  `?.`).
	    -   The two colons of a member reference (`::`).
	-   A method or constructor name stays attached to the open parenthesis (`(`) that follows it.
	-   A comma (`,`) stays attached to the token that precedes it.
	-   A lambda arrow (`->`) stays attached to the argument list that precedes it.

	**Note:** The primary goal for line wrapping is to have clear code, not necessarily code that fits in the smallest number of lines.

	##### Functions
	
	When a function signature does not fit on a single line, break each parameter declaration onto its own line. Parameters defined in this format should use a single indent (+4). The closing parenthesis (`)`) and return type are placed on their own line with no additional indent.
	```kotlin
		fun <T> Iterable<T>.joinToString(
			separator: CharSequence = ", ",
			prefix: \CharSequence = "",
			postfix: CharSequence = ""  
		): String {
			// …  
		}
	```

	##### Expression functions
	
	When a function contains only a single expression it can be represented as an [expression function](https://kotlinlang.org/docs/reference/functions.html#single-expression-functions).
	```kotlin
		override fun toString(): String {
			return "Hey"
		}
	```
	```kotlin
		override fun toString(): String = "Hey"
	```
	The only time an expression function should wrap to multiple lines is when it opens a block.
	```kotlin
		fun main() = runBlocking {
			// …  
		}
	```
	Otherwise, if an expression function grows to require wrapping, use a normal function body, a `return` declaration, and normal expression wrapping rules instead.

	##### Properties
	
	When a property initializer does not fit on a single line, break after the equals sign (`=`) and use an indent.
	```kotlin
		private val defaultCharset: Charset? = EncodingRegistry.getInstance().getDefaultCharsetForPropertiesFiles(file)
	```
	Properties declaring a `get` and/or `set` function should place each on their own line with a normal indent (+4). Format them using the same rules as functions.
	```kotlin
		var directory: File? = null
		set(value) {
			// … 
		}
	```
	Read-only properties can use a shorter syntax which fits on a single line.
	```kotlin
		val defaultExtension: String get() = "kt"
	```

**[⬆ back to top](#table-of-contents)**

- #### Whitespace

	Braces are not required for `when` branches and `if` statement bodies which have no `else if/else` branches and which fit on a single line.

	##### Vertical
	
	A single blank line appears:
	-   _Between_  consecutive members of a class: properties, constructors, functions, nested classes, etc.
		-   **Exception:**  A blank line between two consecutive properties (having no other code between them) is optional. Such blank lines are used as needed to create logical groupings of properties and associate properties with their backing property, if present.
	    -   **Exception:**  Blank lines between enum constants are covered below.
	-   Between statements,  _as needed_  to organize the code into logical subsections.
	-   _Optionally_  before the first statement in a function, before the first member of a class, or after the last member of a class (neither encouraged nor discouraged).
	-   As required by other sections of this document (such as the  [Structure](#structure)  section).

	Multiple consecutive blank lines are permitted, but not encouraged or ever required.

	##### Horizontal
	
	Beyond where required by the language or other style rules, and apart from literals, comments, and KDoc, a single ASCII space also appears in the following places only:
	- Separating any reserved word, such as `if`, `for`, or `catch` from an open parenthesis (`(`) that follows it on that line.
		```kotlin
			// WRONG!  
			for(i in 0..1) {  
			}
		```
		```kotlin
			// Okay  
			for (i in 0..1) {  
			}
		```
	- Separating any reserved word, such as `else` or `catch`, from a closing curly brace (`}`) that precedes it on that line.
		```kotlin
			// WRONG!  
			}else {  
			}
		```
		```kotlin
			// Okay  
			} else {  
			}
		```
	- Before any open curly brace (`{`).
		```kotlin
			// WRONG!  
			if (list.isEmpty()){  
			}
		```
		```kotlin
			// Okay  
			if (list.isEmpty()) {  
			}
		```
	- On both sides of any binary operator.
		```kotlin
			// WRONG!  
			val two = 1+1
		```
		```kotlin
			// Okay  
			val two = 1 + 1
		```
		This also applies to the following “operator-like” symbols:
		- the arrow in a lambda expression (`->`).
			```kotlin
				// WRONG!  
				ints.map { value->value.toString() }
			```
			```kotlin
				// Okay  
				ints.map { value -> value.toString() }
			```

		But not:
		- the two colons (`::`) of a member reference.
			```kotlin
				// WRONG!  
				val toString = Any :: toString
			```
			```kotlin
				// Okay  
				val toString = Any::toString
			```
		- the dot separator (`.`).
			```kotlin
				// WRONG
				it . toString()
			```
			```kotlin
				// Okay  
				it.toString()
			```
		- the range operator (`..`).
			```kotlin
				// WRONG
				for (i in 1 .. 4) print(i)
			```
			```kotlin
				// Okay
				for (i in 1..4) print(i)
			```
	- Before a colon (`:`) only if used in a class declaration for specifying a base class or interfaces, or when used in a `where` clause for [generic constraints](https://kotlinlang.org/docs/reference/generics.html#generic-constraints).
		```kotlin
			// WRONG!  
			class Foo: Runnable
		```
		```kotlin
			// Okay  
			class Foo : Runnable
		```
		```kotlin
			// WRONG  
			fun <T: Comparable> max(a: T, b: T)
		```
		```kotlin
			// Okay  
			fun <T : Comparable> max(a: T, b: T)
		```
		```kotlin
			// WRONG  
			fun <T> max(a: T, b: T) where T: Comparable<T>
		```
		```kotlin
			// Okay  
			fun <T> max(a: T, b: T) where T : Comparable<T>
		```
	- After a comma (`,`) or colon (`:`).
		```kotlin
			// WRONG  
			val oneAndTwo = listOf(1,2)
		```
		```kotlin
			// Okay  
			val oneAndTwo = listOf(1, 2)
		```
		```kotlin
			// WRONG  
			class  Foo :Runnable
		```
		```kotlin
			// Okay  
			class Foo : Runnable
		```
	- On both sides of the double slash (`//`) that begins an end-of-line comment. Here, multiple spaces are allowed, but not required.
		```kotlin
			// WRONG  
			var debugging = false//disabled by default
		```
		```kotlin
			// Okay  
			var debugging = false // disabled by default
		```
	This rule is never interpreted as requiring or forbidding additional space at the start or end of a line; it addresses only interior space.
	
**[⬆ back to top](#table-of-contents)**
	
- #### Specific constructs

	##### Enum classes
	
	An enum with no functions and no documentation on its constants may optionally be formatted as a single line.
	```kotlin
		enum class Answer { YES, NO, MAYBE }
	```
	When the constants in an enum are placed on separate lines, a blank line is not required between them except in the case where they define a body.
	```kotlin
		enum class Answer {
			YES,
			NO,
			
			MAYBE {
				override fun toString() = """¯\_(ツ)_/¯"""
			} 
		}
	```
	Since enum classes are classes, all other rules for formatting classes apply.
	
	##### Annotations
	
	Member or type annotations are placed on separate lines immediately prior to the annotated construct.
	```kotlin
		@Retention(SOURCE)
		@Target(FUNCTION, PROPERTY_SETTER, FIELD)  
		annotation class Global
	```
	
	Annotations without arguments can be placed on a single line.
	```kotlin
		@JvmField @Volatile  
		var disposable: Disposable? = null
	```
	When only a single annotation without arguments is present, it may be placed on the same line as the declaration.
	```kotlin
		@Volatile var disposable: Disposable? = null  
		
		@Test fun selectAll() { 
			// …  
		}
	```
	`@[...]` syntax may only be used with an explicit use-site target, and only for combining 2 or more annotations without arguments on a single line.
	```kotlin
		@field:[JvmStatic Volatile]  
		var disposable: Disposable? = null
	```
	
	##### Implicit return/property types
	
	If an expression function body or a property initializer is a scalar value or the return type can be clearly inferred from the body then it can be omitted.
	```kotlin
		override fun toString(): String = "Hey"  
		// becomes  
		override fun toString() = "Hey"
	```
	```kotlin
		private val ICON: Icon = IconLoader.getIcon("/icons/kotlin.png")  
		// becomes  
		private val ICON = IconLoader.getIcon("/icons/kotlin.png")
	```
	When writing a library, retain the explicit type declaration when it is part of the public API.

**[⬆ back to top](#table-of-contents)**
	
- #### Naming

	Identifiers use only ASCII letters and digits, and, in a small number of cases noted below, underscores. Thus each valid identifier name is matched by the regular expression `\w+`.
	
	Special prefixes or suffixes, like those seen in the examples `name_`, `mName`, `s_name`, and `kName`, are not used except in the case of backing properties (see [Backing properties](#backing-properties)).
	
	##### Package Names
	
	Package names are all lowercase, with consecutive words simply concatenated together (no underscores).
	```kotlin
		// Okay  
		package com.example.deepspace  
		// WRONG!  
		package com.example.deepSpace  
		// WRONG!  
		package com.example.deep_space
	```
	
	##### Type Names
	
	Class names are written in PascalCase and are typically nouns or noun phrases. For example, `Character` or `ImmutableList`. Interface names may also be nouns or noun phrases (for example, `List`), but may sometimes be adjectives or adjective phrases instead (for example `Readable`).
	  
	Test classes are named starting with the name of the class they are testing, and ending with `Test`. For example, `HashTest` or `HashIntegrationTest`.

	##### Function Names
	
	Function names are written in camelCase and are typically verbs or verb phrases. For example, `sendMessage` or `stop`.
	  
	Underscores are permitted to appear in test function names to separate logical components of the name.
	```kotlin
		@Test fun pop_emptyStack() {
			// …  
		}
	```
	Functions annotated with `@Composable` that return `Unit` are PascalCased and named as nouns, as if they were types.
	```kotlin
		@Composable  
		fun NameTag(name: String) {
			// …  
		}
	```
	
	##### Constant names
	
	Constant names use UPPER_SNAKE_CASE: all uppercase letters, with words separated by underscores. But what  _is_  a constant, exactly?

	Constants are  `val`  properties with no custom  `get`  function, whose contents are deeply immutable, and whose functions have no detectable side-effects. This includes immutable types and immutable collections of immutable types as well as scalars and string if marked as  `const`. If any of an instance’s observable state can change, it is not a constant. Merely intending to never mutate the object is not enough.
	```kotlin
		const val NUMBER = 5  
		val NAMES = listOf("Alice", "Bob")  
		val AGES = mapOf("Alice" to 35, "Bob" to 32)  
		val COMMA_JOINER = Joiner.on(',') // Joiner is immutable  
		val EMPTY_ARRAY = arrayOf()
	```
	These names are typically nouns or noun phrases.

	Constant values can only be defined inside of an  `object`  or as a top-level declaration. Values otherwise meeting the requirement of a constant but defined inside of a  `class`  must use a non-constant name.

	Constants which are scalar values must use the  `const`  [modifier](http://kotlinlang.org/docs/reference/properties.html#compile-time-constants).

	##### Non-constant names

	Non-constant names are written in camelCase. These apply to instance properties, local properties, and parameter names.

	```kotlin
		val variable = "var"  
		val nonConstScalar = non-const"  
		val mutableCollection: MutableSet = HashSet()  
		val mutableElements = listOf(mutableInstance)  
		val mutableValues = mapOf("Alice" to mutableInstance, "Bob" to mutableInstance2)  
		val logger = Logger.getLogger(MyClass::class.java.name)  
		val nonEmptyArray = arrayOf("these", "can", "change")
	```
	
	These names are typically nouns or noun phrases.
	
	##### Backing properties
	
	When a [backing property](https://kotlinlang.org/docs/reference/properties.html#backing-properties) is needed, its name should exactly match that of the real property except prefixed with an underscore.
	```kotlin
		private var _table: Map? = null  
	  
		val table: Map
			get() {
				if (_table == null) {
					_table = HashMap()
				}
				return _table ?: throw AssertionError()
			}
	```
	
	##### Type variable names

	Each type variable is named in one of two styles:
	
	- A single capital letter, optionally followed by a single numeral (such as  `E`,  `T`,  `X`,  `T2`)
	- A name in the form used for classes, followed by the capital letter  `T`  (such as  `RequestT`,  `FooBarT`)
	
	##### Camel case
	Sometimes there is more than one reasonable way to convert an English phrase into camel case, such as when acronyms or unusual constructs like “IPv6” or “iOS” are present. To improve predictability, use the following scheme.
	
	Beginning with the prose form of the name:
	
	1. Convert the phrase to plain ASCII and remove any apostrophes. For example, “Müller’s algorithm” might become “Muellers algorithm”.
	2. Divide this result into words, splitting on spaces and any remaining punctuation (typically hyphens).  _Recommended:_  if any word already has a conventional camel-case appearance in common usage, split this into its constituent parts (e.g., “AdWords” becomes “ad words”). Note that a word such as “iOS” is not really in camel case per se; it defies any convention, so this recommendation does not apply.
	3. Now lowercase everything (including acronyms), then do one of the following:
		-   Uppercase the first character of each word to yield pascal case.
		-   Uppercase the first character of each word except the first to yield camel case.
	4.  Finally, join all the words into a single identifier.
	
	Note that the casing of the original words is almost entirely disregarded.
	
	| **Prose form** | **Correct** | **Incorrect** |
	|--|--|--|
	| "XML Http Request" | XmlHttpRequest | XMLHTTPRequest |
	| "new customer ID" | newCustomerId | newCustomerID |
	| "inner stopwatch" | innerStopwatch | innerStopWatch |
	| "supports IPv6 on iOS" | supportsIpv6OnIos | supportsIPv6OnIOS |
	| "YouTube importer" | YouTubeImporter | YoutubeImporter* |
	
	(* Acceptable, but not recommended.)

	**Note:** Some words are ambiguously hyphenated in the English language: for example “nonempty” and “non-empty” are both correct, so the method names `checkNonempty` and `checkNonEmpty` are likewise both correct.

**[⬆ back to top](#table-of-contents)**
	
- #### Documentation

	##### Formatting
	
	The basic formatting of KDoc blocks is seen in this example:

	```kotlin
		/**  
		 * Multiple lines of KDoc text are written here,  
		 * wrapped normally…  
		 */  
		fun method(arg: String) {
			// …  
		}
	```
	...or in this single-line example:
	```kotlin
		/** An especially short bit of KDoc. */
	```

	The basic form is always acceptable. The single-line form may be substituted when the entirety of the KDoc block (including comment markers) can fit on a single line. Note that this only applies when there are no block tags such as `@return`.

	##### Paragraphs
	
	One blank line—that is, a line containing only the aligned leading asterisk (`*`)—appears between paragraphs, and before the group of block tags if present.

	##### Block tags

	Any of the standard “block tags” that are used appear in the order `@constructor`, `@receiver`, `@param`, `@property`, `@return`, `@throws`, `@see`, and these never appear with an empty description. When a block tag doesn’t fit on a single line, continuation lines are indented 4 spaces from the position of the `@`.

	##### Summary fragment
	
	Each KDoc block begins with a brief summary fragment. This fragment is very important: it is the only part of the text that appears in certain contexts such as class and method indexes.

	This is a fragment–a noun phrase or verb phrase, not a complete sentence. It does not begin with "``A `Foo` is a...``", or "`This method returns...`", nor does it have to form a complete imperative sentence like "`Save the record.`". However, the fragment is capitalized and punctuated as if it were a complete sentence.

	##### Usage
	
	At the minimum, KDoc is present for every `public` type, and every `public` or `protected` member of such a type, with a few exceptions noted below.

	##### Exception: Self-explanatory functions
	
	KDoc is optional for “simple, obvious” functions like  `getFoo`  and properties like  `foo`, in cases where there really and truly is nothing else worthwhile to say but “Returns the foo”.

	It is not appropriate to cite this exception to justify omitting relevant information that a typical reader might need to know. For example, for a function named  `getCanonicalName`  or property named  `canonicalName`, don’t omit its documentation (with the rationale that it would say only  `/** Returns the canonical name. */`) if a typical reader may have no idea what the term "canonical name" means!

	##### Exception: overrides
	
	KDoc is not always present on a method that overrides a supertype method.

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

