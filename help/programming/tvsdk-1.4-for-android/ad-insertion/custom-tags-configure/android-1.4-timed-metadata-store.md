---
description: Your application must use the appropriate TimedMetadata objects at the appropriate times.
seo-description: Your application must use the appropriate TimedMetadata objects at the appropriate times.
seo-title: Store timed metadata objects as they are dispatched
title: Store timed metadata objects as they are dispatched
uuid: 0e6d2a42-37a8-477e-b925-66bbc23445c1
---

# Store timed metadata objects as they are dispatched {#store-timed-metadata-objects-as-they-are-dispatched}

Your application must use the appropriate TimedMetadata objects at the appropriate times.

 During content parsing, which happens before playback, TVSDK identifies subscribed tags and notifies your application about these tags. The time that is associated with each `TimedMetadata` is the local time on the playback timeline.

Your application must complete the following tasks: 

1. Keep track of the current playback time.
1. Match the current playback time to the dispatched `TimedMetadata` objects.

1. Use the `TimedMetadata` where the start time equals the current local playback time.

   The following example shows how to save `TimedMetadata` objects in an `ArrayList`. 

   ```java
   private List<TimedMetadata> _timedMetadataList = new ArrayList<TimedMetadata>(); 
   ... 
   public void onTimedMetadata(TimedMetadata timedMetadata) { 
       ... 
       if (timedMetadata.getName().equalsIgnoreCase("#EXT-X-CUE"))  { 
           _timedMetadataList.add(timedMetadata); 
       } 
       ... 
   }
   ```

