# Functions
Function definitions and calls became wide and complex situation since we got exotic syntaxes for anonymous, lambdas etcetera... Formatting habits did not evolve accordingly and made most late java code rather difficult to grasp.



### Functions definitions
```java
// Classic (e.g. a constructor)
public CGTSMessage(long deviceID, String messageType, double latitude, double longitude)
{
    super();
    ...
}

// Example of Solving the too many parameters problem
public CGTSMessage
(
    long deviceID, String messageType,
    double latitude, double longitude
)
{
    super();
    ...
}

// Or even
public CGTSMessage
(
    long deviceID,
    String messageType,
    double latitude,
    double longitude
)
{
    super();
    ...
}

// Trivial code using inline style. 
// The tabular style is recommended for aligning list of similar functions
public double getLatitude()                    { return latitude;                }
public void setLatitude(double latitude)       { this.latitude = latitude;       }
public double getLongitude()                   { return longitude;               }
public void setLongitude(double longitude)     { this.longitude = longitude;     }

// We can use the 'breakink long line with short indent' as well
public void setLatitude(double latitude)       
  { this.latitude = latitude; }
public void setLongitude(double longitude)     
  { this.longitude = longitude; }
```
### Functions calls
```java
// Classic 
TimeZone tz = calendar.getTimeZone();

// Embedded long call with enhanced readability 
DebugLogAndPrint
(
    String.format
    (
        "THREAD START ('%s') at: %s",
        getName(),
        Calendar.getInstance().getTime().toString()
    )
);

// lambdas
// ==> Let's avoid this
shutdownManager.addShutdownHook(() -> {
    producer.close();
    // give a bit of time to stop..
    Thread.sleep(200);
});

// ==> Try this much clearer version instead
// parenthesis are first class blocks delimiters
// closing a block with '});' becomes unacceptable.
shutdownManager.addShutdownHook
(
    () -> 
    {
        producer.close();
        // give a bit of time to stop..
        Thread.sleep(200);
	}
);

```