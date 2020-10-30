# A new Java Coding Style Manifesto
For a modern Java code formatting style

## Introduction
For a modern Java code formatting style
Let's be clear, this manifesto is for advocating a Java formatting style opposing K&R C inventors advocated by [google](https://google.github.io/styleguide/javaguide.html).

When comparing to the existing languages at that time (PASCAL, COBOL, ADA...), K&R did not fully took advantage of their newly introduced typographic block delimiters: '{' and '}'.

Java evolutions with anonymous classes, functional interfaces, lambdas... makes this even more obvious: old style formatting became definitely outdated.

Let' s look at the first formatting examples from google guide we just mentioned above:

```java
return new MyClass() {
  @Override public void method() {
    if (condition()) {
      try {
        something();
      } catch (ProblemException e) {
        recover();
      }
    } else if (otherCondition()) {
      somethingElse();
    } else {
      lastThing();
    }
  }
};
```
The proposed new formatting rules will result in a much better code organization perception:

```java
return new MyClass() 
{
    @Override public void method() 
    {
        if(condition()) 
        {
            try 
            {
                something();
            } 
            catch(ProblemException e) 
            {
                recover();
            }
        } 
        else if(otherCondition()) 
        {
            somethingElse();
        } 
        else 
        {
            lastThing();
        }
    }
};
```
And will also allow its equivalent compact format:

```java
return new MyClass() 
{
    @Override public void method() 
    {
        if(condition()) 
        {
            try{something();} 
            catch(ProblemException e){recover();}
        } 
        else if(otherCondition()) somethingElse();
        else lastThing();
    }
};
```
which is still much more readable in terms of catching code structures at first glance.
