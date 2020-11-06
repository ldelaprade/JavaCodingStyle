# Simple constructs


### Classes/Abstracts/Interfaces


```java
public interface SQLTableInterface
{
    ...
}
```
Breaking long lines need no indentations. For example:

```java
public class DualTable extends OracleSpec implements SQLTableInterface
{
    public DualTable() 
    {
        ...
    }
    ...
}
```
Can be put this way (avoid useless indent  - don't have to get excuse for being this long line - spreading right or down should be considered equivalent):

```java
public class DualTable 
  extends OracleSpec 
  implements SQLTableInterface
{
    public DualTable() 
    {
        ...
    }
    ...
}

```

### if/while/do/for


```java
// 'if' regular form
if(anonymous)
{
    env.put(Context.SECURITY_AUTHENTICATION, "none");
    env.put(Context.SECURITY_PRINCIPAL, "");
    env.put(Context.SECURITY_CREDENTIALS, "");
}
else
{
    String classificationOU = guessUserSearchOU(lowerCaseLogin, ldapActiveMode);
    String ldapAuth = String.format(ldapUserSearch, lowerCaseLogin, classificationOU);
    env.put(Context.SECURITY_AUTHENTICATION, "simple");
    env.put(Context.SECURITY_PRINCIPAL, ldapAuth);
    env.put(Context.SECURITY_CREDENTIALS, password);
}

// 'if' semi compact form
public static boolean isEuristicalyTrue(Object value)
{
    if(value != null)
    {
        if(value.getClass().equals(Boolean.class))
            return safeCast(value, Boolean.TYPE);
        else if(isNumeric(value.toString()))
            return (Integer.parseInt(value.toString())!=0);
        else
            return value.toString().matches("(?i)true|(?i)yes");
    }
    return false;
}

// 'if' ultra compact form for trivial situations
public static class IgnoreCaseComparatorForString implements Comparator<String>
{
    @Override
    public int compare(String o1, String o2)
    {
        if(o1 == null)      return -1;
        else if(o2 == null) return 1;
        else                return o1.compareToIgnoreCase(o2);
    }
}

// 'do while' format
do
{
    JetSQLColumnsInterface f = orderedFields.get(i);
    if(f != null)
        ProcessOneItem(orderedFields.get(i));
}
while(++i < iSize);

// while format
while(result.hasNext())
{
    JetSQLFieldValues record = result.next();
    Object value = record.getFieldValue(column);
    if(value!=null)
        mapResult.put(value, record.getFieldValueAsString(column));
}

// Classic for
for(int i = 0; i < roots.length ; i++)
{
    System.out.println("exploring root path ==> " + roots[i]);
    Path currentExploredPath = Paths.get(roots[i].getAbsolutePath());
}
        
// Modern for
for(Object f : sqlObjset)
{
    int indexPosition = ((JetSQLColumnsInterface)f).getSelectFieldPosition();
    maxIndex = Math.max(indexPosition, maxIndex);
    orderedFields.put(indexPosition, (JetSQLColumnsInterface)f);
}
```

### try/catch/finally


```java
if(!processWasStarted)
{
    try
    {
        processWasStarted = true;
        lengthyOperation();
    }
    catch(final Exception e)
    {
        OnException(e);
    }
    finally
    {
        // When we are here, task is complete
        cleanExit();
    }
}

```


```java



```