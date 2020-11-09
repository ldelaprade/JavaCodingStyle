# Introduction
This manifesto is promoting a modern Java formatting style contrasting with K&R C oldish style applied to Java and advocated by most java open source tenants including  [google](https://google.github.io/styleguide/javaguide.html).

When comparing to the existing languages at that time (PASCAL, COBOL, ADA...), K&R did not fully took advantage of their newly introduced typographic block delimiters: '{' and '}'.

Java evolutions with anonymous classes, functional interfaces, lambdas... makes this even more obvious: old style formatting became definitely outdated.

Let's have a look at the first formatting example found in google site just mentioned above:

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
The proposed new formatting rules will result in a much better code organization and better perception:

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
And will also allow its equivalent compact format
which is still much clearer.

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

