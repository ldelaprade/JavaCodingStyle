# A new Java Coding Style Manifesto
For a modern Java code formatting style

## Introduction
For a modern Java code formatting style
Let's be clear, this manifesto is for advocating a Java formatting style opposing K&R C inventors advocated by [google](https://google.github.io/styleguide/javaguide.html).

K&R did not fully realized the impact of introducing typographic block delimiters: {, (, [.

Java evolutions with anonymous classes, functional interfaces, lambdas... makes old style formatting completely outdated

Let' s look at the first examples showing at google guide just mentioned:

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
The proposed new formatting rules will result in a much higher readability:

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
but will also allow a compact format:

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
which is still much more readable in terms of code structures organization immediate perception.
