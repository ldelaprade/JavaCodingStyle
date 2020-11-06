# Annotations

Annotations deserves same level of clarity and should be considered as regular code. Braces and Parenthesis implies same block formatting structures as for regular code.


```java
@JetMenuGroupConfig
(
    ID = "MENU_DASHBOARD", Label = "Data Browsing",    Icon = "dashboard.png",
    menuItems =
    {
        @JetMenuItemConfig
        (
            ID = "JET_CMD_EVENTS_MONITORING",  
            Label = "Events monitoring",
            Icon = "grid24.png",
            Description = "Monitoring system events"
        ),
    }
)
@JetMenuGroupConfig
(
    ID = "MENU_OPERATIONS", Label = "Operator tasks",    Icon = "operatorTasks.png",
    menuItems =
    {
        @JetMenuItemConfig
        (
            ID = "JET_CMD_OMU_EVENT_ALERT",
            Label = "Event/alert infos",
            Icon = "led-square-grey-25.png",
            Description = "Event/alert information"
        ),
        @JetMenuItemConfig
        (
            ID = "JET_CMD_OMU_ACTIVE_TABLES",
            Label = "Active tables mngmnt",
            Icon = "led-square-grey-25.png",
            Description = "Active tables and hung alerts management"
        ),
    }
)
public class JetMenuEngine
{
    ...
}  
```
