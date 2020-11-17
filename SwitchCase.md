# Switch Case (and ternary operator)

Switch/case and ternary operator ('?') surely deserve special consideration. Both are particular coding structures. This causes wide range of different coding styles ever found compared to simpler structures. 

### switch/case

For the 'switch' part, no surprise -  we stick to the if/while braces positions. The 'cases' part reminds us good old GOTO tag labels (somehow deprecated but still available in C/C++ !). 

Here's what we think is the simplest and best approach to adopt.


```java
// switch/case standard (avoiding useless indent and additional braces)
switch(commandID)
{
    case "JET_CMD_OMU_CONFIG":
    JetOmuConfigurationUI wizCfg = new JetOmuConfigurationUI();
    wizCfg.ShowPopupWizard("Jet Configuration settings Wizard");
    break;

    case "JET_CMD_HIST_CONFIG":
    JetOmuHistoryUI wizHistCfg = new JetOmuHistoryUI();
    wizHistCfg.ShowPopupWizard("Jet History maintenance Wizard");
    break;

    default:
    break;
}

// Avoid this confusing style with useless block braces delimiters. 
// 'break' inside or outside braces would mean the same...
case "JET_CMD_OMU_CONFIG":
{
    JetOmuConfigurationUI wizCfg = new JetOmuConfigurationUI();
    wizCfg.ShowPopupWizard("Jet Configuration settings Wizard");
    break; // break here ?
}
break; // break here ?
```

### ternary operator

Good formatting options for the ternary operator will greatly help readability - therefore encouraging its usage in more situations.


```java
// Parethesing - though optional - helps visual logic
AddLabelField((isESL ? "Esl customer: " : (isOML ? "OM Group: " : "Any: "));

// Parethesing + multilines structures helps even more
setValue
(
    isESL ?
    (
        "Further nodes filtering (optional)"
    )
    :
    (
        isOML ?
        "Click next for OM nodes"
        :
        "Click next to load from file."
    )
);

// Where most developers wouldn't dare and would instead use a switch/case, 
// here is the 'smart style'.
// It makes things even clearer and shorter than a switch/case: 
severityText=
(
    severity==0 ? "normal"    :
    severity==1 ? "warning"   :
    severity==2 ? "minor"     :
    severity==3 ? "major"     :
    severity==4 ? "critical"  : "unknown"
);
```
An Oracle SQL DECODE code would look very similar...
```SQL
SELECT
    DECODE
    (
        STATUS,
        0     ,    'Processed',
        1     ,    'Added'    ,
        2     ,    'Deleted'  ,
        3     ,    'Updated'  , 'Invalid'
    )
    AS STATUS_TXT
FROM MY_TABLE
```

