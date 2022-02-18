# JUnit 5: Changes, Efficiencies, and More

| Version | Changelog
|---------|----------------
| 1.0.0 | [Changelog](CHANGELOG.md)

## Overview

Unit testing and test driven development have now become part of every developer's skill set. 
For Java developers, the most popular testing tool has been JUnit, and JUnit 5 is built using the latest features of Java.  
With Java Unit Testing with JUnit 5, you'll master these new features, including method parameters, extensions, assertions and assumptions, 
and dynamic tests. You'll also see how to write clean tests with less code.

### High-level

* Write tests the JUnit 5 way
* Run your tests from within your IDE
* Integrate tests with your build and static analysis tools
* Migrate from JUnit 4 to JUnit 5


### Who is session / primer is for
Java developers with Java 8 experience (e.g. Lambdas), and any level of unit testing experience.

### Before Starting
Consider reading the [Introduction to JUnit 5](./INTRO.md) for a background on its features, architecture, and rationale behind the updated
testing framework.

### JUnit 5 Changes from JUnit 4
* **JUnit 5 test classes and test methods are not required to be public**: 
In JUnit 5, a few of these constraints have been relaxed.
We can now make them package protected as shown in the code that follows:
```java
// package and import statements removed for brevity

class BookShelfSpec {
    
  @Test
  void shelfEmptyWhenNoBookAdded(){
        BookShelf shelf = new BookShelf();
        List<String> books = shelf.books();
        assertTrue(books.isEmpty(), () -> "BookShelf should be empty.");
    }
}
```

* **JUnit 5 Test Constructor are allowed to have parameters**: Test methods can have not only constructors but also parameters. 
This is achieved by providing a `ParameterResolver`. A `ParameterResolver` dynamically resolves parameters at runtime:

```java
class BookShelfSpec {

    private BookShelfSpec(TestInfo testInfo) {
        System.out.println("Working on test " + testInfo.getDisplayName());
    }

    // test method removed for brevity

}
```

* **@DisplayName**: This annotation allows us to be more descriptive in nature.

```java
@DisplayName("A bookshelf")
class BookShelfSpec {

    @Test
    @DisplayName("is empty when no book is added to it")
    void shelfEmptyWhenNoBookAdded() {
        BookShelf shelf = new BookShelf();
        List<String> books = shelf.books();
        assertTrue(books.isEmpty(), () -> "BookShelf should be empty.");
    }

}
```

## Examples

| Link | Description |
|---------|----------------|
| TODO | TODO |

## Support Channels

## Links

## Appendix
[1]: Citation from [Shekhar Gulati and Rahul Sharma, Java Unit Testing with JUnit 5](https://doi.org/10.1007/978-1-4842-3015-2_1)
