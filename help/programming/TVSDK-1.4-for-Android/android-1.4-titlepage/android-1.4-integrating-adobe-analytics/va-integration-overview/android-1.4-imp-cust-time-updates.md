---
description: In some analytics implementations, the client application might want to provide a different playhead position than the position reported by the TVSDK localTime value. For example, during a linear stream playback, each program’s playhead can be provided relative to its start time.
seo-description: In some analytics implementations, the client application might want to provide a different playhead position than the position reported by the TVSDK localTime value. For example, during a linear stream playback, each program’s playhead can be provided relative to its start time.
seo-title: Implement custom time updates
title: Implement custom time updates
uuid: eebba18d-33e6-472e-972b-1e364e4e8739
index: y
internal: n
snippet: y
---

# Implement custom time updates{#implement-custom-time-updates}

In some analytics implementations, the client application might want to provide a different playhead position than the position reported by the TVSDK localTime value. For example, during a linear stream playback, each program’s playhead can be provided relative to its start time.

>[!TIP]
>
>Override this method only if you want to provide a playhead position other than the default position.

1. To override the default playhead position:

   ```java
   vaMetadata.setCurrentTimeUpdateBlock(new VideoAnalyticsMetadata.CurrentTimeUpdateBlock() { 
       @Override 
       public long call() { 
           long range = 500L; 
           Random r = new Random() 
           return (long)(r.nextDouble()*range); 
       } 
   });
   ```

   >[!IMPORTANT]
   >
   >The values in this code snippet are only samples. You need to use different values for your custom playhead position.
