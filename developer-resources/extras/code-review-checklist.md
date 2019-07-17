# Code Review Checklist



### Code Review Checklist

#### Overview:

This intent of this document is not to dictate or restrain how you write code, rather it’s intended to be a guide to help you write better code. The document starts with a short list of items to look for when conducting code reviews. The list below identifies, objectively, common programming faults and follies. The rest of this document goes into more detail on these “code smells” and provides some guidance as to how these problems can be avoided.

**Rule of Thumb: “A code review should only judge the clarity and substance of the code – not the style.”** It is important to note that we are not reviewing the style of coding, only whether that code violates best practices or potentially introduces performance or maintenance issues. To sum up, _**if the code can stand on its own \(is understandable without explanation\)**_, there are no potential faults from performance or maintenance issues, and has proper unit tests - it should pass code review.

**During code review**

* Critique the code, not the coder
* Relate comments to standards, specs, performance etc.
* Avoid “Why didn’t you” and replace with “What was the reasoning behind the deviation of standards here..”
* Code formatting is important and style, to a certain extent, is as well, but style should not be the basis for rejecting otherwise readable and valid code.
* Does the code implement the design?
* Is the code easily understandable?
* Is the code developed using a TDD approach, or at the very least have tests for code written / modified?

**Reasons for Rejecting Code:**

* Unit test code coverage doesn’t cover the code under review.
* Code doesn’t compile / doesn’t function as expected \(smoke test\).
* Code that doesn’t follow:

| Don'ts | Do's |
| :--- | :--- |
| Long parameter lists \(&gt;3 params\) | Code should follow SOLID principles |
| Null checks |  |
| Unnecessary comments / commented-out code |  |
| Magic numbers / strings |  |
| Object instantiation |  |
| Duplicate code |  |
| Combinatorial explosion |  |
| Large classes |  |
| Type names embedded in names |  |
| Uncommunicative Names |  |

**Overview / Guidelines**

* Code should be reviewed before being made available to QA
* During development
  * Static code analysis should be run to ensure:
    * Code adheres to recognized standards and coding styles
    * Doesn’t introduce security issues
  * Developer should strive to produce code that meets the business need and is easy to maintain
  * Developed using a TDD approach, or at the very least have tests for code written

**Code Smells Detail** - warnings, something that should be reviewed in detail

* Consider using null object pattern instead of null checks
* If there is a comment above a variable or method that does a better job explaining the functionality of the variable or method name, consider changing the name of the variable or method to be more descriptive.
* NO magic numbers, magic strings,
  * Instead try Enums, constant numbers/strings with meaningful names.
* NO commented-out code
  * Instead write more descriptive check-in comments when removing 
* If you see the word **new** \(constructing an object\)
  * Instead declare dependencies through constructor arguments that are of the type's interface
* Coding should in most cases be done against interfaces
* If you need to scroll to see the entire contents of a procedure or method:
  * It is likely too complex and may benefit from being broken down into smaller pieces.
* Specific-Case Code Smells:
  * **Duplicate Code:** Don’t repeat yourself; if you are doing the same thing in more than one spot, extract it to a method.
  * **Combinatorial Explosion:** When you see a lot of code doing _almost_ the same thing, it may be a case of combinatorial explosion, a form of repeating code.  Consider refactoring methods to interfaces or make use of generics. 
  * **Long Parameter List:** If you see a method that takes 4 or more arguments it may be too complex - and it will definitely prove difficult to test.  Aim for smaller functions that take 0-2 arguments, if possible, OR consider combining the parameter list into an object.
  * **Large Class:** A bunch of smaller more focused classes are preferable to a large and complex single class.  If you encounter a large class consider refactoring it out into smaller more easily testable classes.
  * **Types Embedded in Names:** Don’t put the type of the variable in the name since the variable’s name will need to change if its type changes.
  * **Uncommunicative Name:** Methods should describe what they do in their name, variable names should describe the value they hold.  If the method name says it does one thing, but appears to do many things, that can mislead you and cause bugs.  When naming a method, keep it descriptive, if the name is too long, it’s likely doing too much.

**Standardization:** Follow standard naming and coding conventions

* Apex 
  * [Naming Conventions](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_classes_naming_conventions.htm) 
  * [Java Style Guide ](https://google.github.io/styleguide/javaguide.html) 
  * [Apex Coding Conventions](https://gist.github.com/KorbenC/24f04b4d0f4bcf65ce5a)
  * Additional Resources:
    * [Apex Coding Best Practices](https://developer.salesforce.com/index.php?title=Apex_Code_Best_Practices&oldid=26951)
    * [Apex Design Patterns](https://developer.salesforce.com/page/Apex_Design_Patterns)
    * [Architecture Developer Center](https://developer.salesforce.com/developer-centers/architecture/)
    * [Apex Test Class Best Practices](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_testing_best_practices.htm)
    * [SOQL and SOSL Best Practices](https://developer.salesforce.com/docs/atlas.en-us.salesforce_large_data_volumes_bp.meta/salesforce_large_data_volumes_bp/ldv_deployments_best_practices_soql_and_sosl.htm)
    * [Execution Governors and Limits](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_gov_limits.htm)

**Javascript:**

* Leverage online tools for quickly checking code [JSHint](https://jshint.com/) [JSMeter](https://github.com/wahengchang/js-meter#readme)
* Avoid anonymous callback functions, especially nested anonymous callback functions, \(which are not testable\) and instead call public functions on the return of asynchronous code.
* _use strict_ should be set 
* Variable Declaration
  * Check to see if variable declaration is inline with variable hoisting

**Items addressed by Human Code Review:**

* Questions to ask
  * Did the method you modified become easier or harder to maintain after you added your changes?

