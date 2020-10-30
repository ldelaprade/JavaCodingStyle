# Driving principles


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

Considering 'THEN' keyword the opening block delimiter, then, being matched with the newly introduced '{', no wonder it was first translated into such C styling:
```c
if(a<b) {
  DISPLAY("COMBINED CONDITION");
} else {
  DISPLAY("NAH");
}    
```

This missed the fact that older languages blocks start/end visual matching was based on words only. The above COBOL sample have the 'IF' aligned with 'ELSE' and 'END-IF'.
The corresponding C translation is messing it all. Mixing the new C blocks delimiters typographic signs with the 'if', 'else' misused as delimiters here. The eye will have difficulties catching block structures here.

That's why - for clear coding and obvious reading -  proper open/close delimiters alignment will be a better C translation of the above COBOL styling.
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