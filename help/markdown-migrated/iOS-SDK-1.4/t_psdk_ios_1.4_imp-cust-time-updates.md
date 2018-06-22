---
description: In some analytics implementations, the client application might want to provide a different playhead position than the position that is reported by the ’s localTime value. For example, during a linear stream playback, each program’s playhead can be provided relative to its start time.
seo-description: In some analytics implementations, the client application might want to provide a different playhead position than the position that is reported by the ’s localTime value. For example, during a linear stream playback, each program’s playhead can be provided relative to its start time.
seo-title: Implement custom time updates
title: Implement custom time updates
---

# Implement custom time updates

>[!TIP]
>
>Override this method only if you want to provide a playhead position that is different from the default position.
>1. To override the default playhead position:
>   ```
>   vaTrackingMetadata.currentTimeUpdateBlock = ^CMTime () { 
>    NSInteger random = arc4random() % 500; 
>    return CMTimeMakeWithSeconds(random, 1); 
>   };
>   ```
>   >[!IMPORTANT]
>   >
>   >In this code sample, 500 is only a sample value. You need to use a different value for your custom playhead position.
>   
>   
>   