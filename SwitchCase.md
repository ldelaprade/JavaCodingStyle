# Switch Case

Switch case deserve a special consideration because it's the most difficult construct to get formatting consensus on. For the switch part, no surprise -  we stick to the if/while braces positions. The cases part has no equivalent on other constructs and readability and simplicity considerations lead us to what follows.


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

// This would be confusing and useless braces. break inside or outside braces would mean the same...
case "JET_CMD_OMU_CONFIG":
{
    JetOmuConfigurationUI wizCfg = new JetOmuConfigurationUI();
    wizCfg.ShowPopupWizard("Jet Configuration settings Wizard");
    break; // break here ?
}
break; // break here ?
    
```
