---
---

<a id="section_42EB6D62627A424ABA250E3246EFEFC3"></a>

Each `codeph TimeRange` specification in the set represents a segment on the playback timeline that is maintained internally by  and that must be appropriately marked as an ad-related period.

The `codeph TimeRange` class is a simple data structure that exposes the start position and the end position on the timeline. These two read-only properties abstract the idea of a time range in the playback timeline.
>[!TIP]
>
>Both values are expressed in milliseconds.

Here is a summary of the `codeph TimeRange` class:
```java
public final class TimeRange {
 // the start/end values are provided at construction time
 public static TimeRange createRange(long begin, long duration) {...} 

 // only getters are available
 public long getBegin() {...} 
 public long getEnd() {...} 
 public long getDuration() {...}
}

```
