- Recap how and why we pair program
- Understand why we test what we should test
- Know what makes up a test
- Know how we can use packages in a project
- Introduce jest - a popular testing framework
- JSON stands for JavaScript object notation

# Pairing
- Driver and Navigator
- Industry Standard
- Learn from someone else
- Navigator has the final decision
- 2 heads are better than one
- Different perspectives
- Collaboration
- Practice with GitHub


----- 
- Stick to your role
- Agree how often you will switch but do it regularly
- Agree how often you will take breaks
- Discuss how you would like your code to be reviewed
- If you don't agree on the approach go with the navigator
- If you are comfortable to do so, allocate time for an end of session review
- Be kind

## Driver
- Types
- Decides on syntax
- implements the navigators ideas
## Navigator
- chooses the direction
- reviews the code as we go
- spots errors in syntax

## Why do companies pay money for pairing?
1. Increased code quality
2. Better productivity
3. Knowledge sharing
4. Cost effective!!

## Why do we do it on the boot-camp?
1. Learning from one another
2. Active learning process
3. Better communication skills
4. It is expected by recruitment partners

# Testing
- The boot-camp focuses on test driven development
- We will focus on unit testing during fundamentals, testing individual functions

## Why
1. Prevent bugs
2. Ensure correct functionality
3. Validate changes
4. Give us confidence
5. Provide documentation
6. Break down complex problems

## What
1. Behaviour not implementation
2. simple -> complex
3. Core functionality
4. Edge Cases

## Anatomy of a test

### Description
-Human readable
-Explains what it means if the test passes
### Assertion
-A comparison of what your code does versus what you want it to do



# Using packages
## Package manager
- Software that manages the installation of packages within a project
- we will use npm(node package manager)


## Package
- A collection of code usually from a third party and added to a project

## Dependency
- Once installed it is said to be a dependency of our project
- Developer(dev) dependency is only require for the development of our code

## Script
- a set of predefined commands or tasks that can be executed using the npm command line interface(in the context of npm and node)

# Jest Syntax
- Describe(string, function) - groups a set of tests together
- test(string function) - defines an individual test case
- expect(actualValue) - allows us to state our assertion
- .toBe(expectedValue) checks our assertion (actual === expected)

```js
function sumNums(num1, num2){return }

describe("group of tests", function() { // desc of group
	test("what we are testing"), function(){ // desc of test
		const actual = sumNums(5,5)
		expect(actual).toBe(10)
	}
})
```
- running npm test will run the tests that are in {filename}.test.js

## test cycle
- Write a failing test
- Make the test pass
- Refactor