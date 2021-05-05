# JUnitIn28Minutes

Reference: Udemy course and it's forked repo.: 
[https://www.udemy.com/course/junit-tutorial-for-beginners-with-java-examples/](https://www.udemy.com/course/junit-tutorial-for-beginners-with-java-examples/)


## Get started with Junit

* [Course Overview](#topics)
  - [Section 1 Foundation](#section-1-foundation)
  - [Section 2 First JUnit Example](#section-2-first-junit-example)
  - [Section 3 Second JUnit Example](#section-3-second-junit-example)
  - [Section 4 JUnit Simple Test Scenarios](#section-4-junit-simple-test-scenarios)
  - [Section 5 JUnit Intermediate Test Scenarios](#section-5-junit-intermediate-test-scenarios)
  - [Section 6 JUnit Best Practices](#section-6-junit-best-practices)
  - [Starting Examples](#starting-examples)
* [About in28Minutes](#about-in28minutes)
  - [Our Beliefs](#our-beliefs)
  - [Our Approach](#our-approach)
  - [Find Us](#useful-links)
  - [Other Courses](#other-courses)

## Topics
### Section 1 Foundation
- What is Unit Testing?
- What is Regression Testing?
- Automation Testing
	- Process of testing the software through automated testcases written in software. 
	- Multiple tools/Frameworks are generally used for automating the process and repeating the test cases. 
	- Reduces human intervention 
	- Increases the success rate of the tests.
	- Improves efficiency of teams.

	
- What is JUnit?
	- Java unit testing framework
	- One of the best test methods for unit/regression testing.
	- An open-source framework
	- Used to 
		- Write and run repeatable automated tests.
		- CI/CD
		- Trigger automated processes etc.

	- Masters in writing the repeatable test cases.

- Why Unit Testing?

### Section 2 First JUnit Example
@Test Annotation
	https://junit.org/junit4/javadoc/4.12/org/junit/Test.html
	Converts a method into a test case.
	Junit execution engine understands it as a test case and executes it.
	Executes 
		after the @Before code has been executed (if you have placed it).
		
- Running JUnit
- No Failure = Success
- Basic Assert methods
	https://junit.org/junit5/docs/5.0.1/api/org/junit/jupiter/api/Assertions.html

### Section 3 Second JUnit Example
- assertTrue and assertFalse methods
	- assertTrue: Asserts that the supplied condition is true.
	- assertFalse: Asserts that the supplied condition is not true
- @Before @After annotations
	- @Before: Before annotation 
		Execute before EVERY test in JUnit. 
		Used to setup the infrastructure before the test executions. 
		e.g. create some primary object before actual execution happens
	- @After: After annotation
		Executed after EVERY testcase is executed. 
		Used to destroy/cleanup the variables/infrastructure and free up the memory.
		
	
	
- @BeforeClass @AfterClass annotations
	- @BeforeClass: The BeforeClass annotation 
		- Execcuted ONCE before running all the tests. 
		- Must be static.
	- @AfterClass: AfterClass annotation 
		- Executed after ALL test cases in the class is executed.


### Section 4 JUnit Simple Test Scenarios
- Comparing Arrays
	- https://junit.org/junit5/docs/5.0.1/api/org/junit/jupiter/api/Assertions.html
- Testing Exceptions
	- https://junit.org/junit5/docs/5.0.1/api/org/junit/jupiter/api/Assertions.html
	- assertThrows
	- assertTimeout
	- e.g.  Assertions.assertThrows(NumberFormatException.class, () -> {
    			Integer.parseInt("One");
  		});

### Section 5 JUnit Intermediate Test Scenarios 
- Parameterized Tests
  	- https://www.baeldung.com/parameterized-tests-junit-5 
- Test Suites
	Junit4 Test Suites: https://howtodoinjava.com/junit/how-to-execute-junit-testcases-in-test-suite/
	Junit5 Test Suites: https://howtodoinjava.com/junit5/junit5-test-suites-examples/
### Section 6 JUnit Best Practices
- Naming Test Methods
- Highlight Important Values in Tests
- Handle Exceptions Properly
- Readable Assert Statements

### Other details
- @DisplayName
	- Added in Junit5. @DisplayName("Provide a detailed desciption")  
- s

### Starting Examples
```
package com.in28minutes.junit.helper;

public class StringHelper {

	public String truncateAInFirst2Positions(String str) {
		if (str.length() <= 2)
			return str.replaceAll("A", "");

		String first2Chars = str.substring(0, 2);
		String stringMinusFirst2Chars = str.substring(2);

		return first2Chars.replaceAll("A", "") 
				+ stringMinusFirst2Chars;
	}

	public boolean areFirstAndLastTwoCharactersTheSame(String str) {

		if (str.length() <= 1)
			return false;
		if (str.length() == 2)
			return true;

		String first2Chars = str.substring(0, 2);

		String last2Chars = str.substring(str.length() - 2);

		return first2Chars.equals(last2Chars);
	}

}

```

