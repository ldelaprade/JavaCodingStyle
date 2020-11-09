# Switch Case

Switch case deserve a special consideration. For the switch part, no surprise -  we stick to the if/while braces positions. The cases part looks like is the remaining part of our good old GOTO tag labels (which is deprecated but still available in C !). 

Here's what we think is the simplest and best approach to adopt.


### switch/case


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
