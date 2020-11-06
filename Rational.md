# Driving rational


## Blocks

K&R approach to block formatting inherits from older languages where opening block has no dedicated typographies.

COBOL example: 

```cobol
IF NUM1 IS LESS THAN NUM2 AND NUM1 IS LESS THAN 100 THEN
    DISPLAY 'COMBINED CONDITION'
ELSE
    DISPLAY 'NAH'
END-IF    
```

Considering 'THEN' keyword the opening block delimiter. 'THEN', being matched with the newly introduced '{' - no wonder it was first transposed to such C styling:

```c
if(a<b) {
   DISPLAY("COMBINED CONDITION");
} else {
    DISPLAY("NAH");
}    
```

This missed the fact that older languages blocks start/end visual matching was based on words only. The above COBOL sample have the 'IF' aligned with 'ELSE' and 'END-IF'.
The corresponding C translation is messing it all. It is mixing the new C blocks delimiters typographic signs with the 'if'/'else' delimiters. Hence the difficulties for catching block structures immediately.

That's why - proper open/close '{' and '}' delimiters horizontal alignment will be a better C translation of the above COBOL styling.
```c
if(a<b) 
{
    DISPLAY("COMBINED CONDITION");
}
else 
{
    DISPLAY("NAH");
}    
```

## Parenthesis

Since java evolution with anonymous class, functions and lambdas, parenthesis get promoted to be first class block delimiter citizens. This enable much more creative readability options, breaking the current narrowminded parenthesis style we can see all over enterprise and open source repositories. 

Clarity first:

```java
if
(
    StringUtils.isBlank(fldCiDesc.getValue())
    &&
    StringUtils.isBlank(fldCustomer.getValue())
    &&
    StringUtils.isBlank(fldDataCenter.getValue())
)
{
    JetNotifs.DoVaadinWarnNotif("Try to narrow your search criteria.");
}
```
and uninhibited function call styles... !

```java
EslResultForClipboard.setValue
(
    String.format
    (
        String.join
        (
            "\n",
            "ESL Node: %s",
            "CI Status: %s",
            "Assignment Goup: %s",
            "Service Level: %s"
        )
        ,
        ecs[0].NodeName,
        ecs[0].Status,
        ecs[0].AssignmentGroup,
        ecs[0].ServiceLevel
    )
);
```

## Lines length

Long lines breaking would be made obvious by indenting post-breaks. However, as regular indent are made of 4 spaces - long line breaks will hold 2 spaces only.


```java
// long line version
public class DualTable extends OracleSpec implements SQLTableInterface
{
    ...
}
// long line breaked using 2 spaces indent
public class DualTable 
  extends OracleSpec 
  implements SQLTableInterface
{
    ...
}
```
