---
description: When you reset a MediaPlayer instance, it is returned to its uninitialized IDLE state as defined in MediaPlayerStatus.
seo-description: When you reset a MediaPlayer instance, it is returned to its uninitialized IDLE state as defined in MediaPlayerStatus.
seo-title: Reset or reuse a MediaPlayer instance
title: Reset or reuse a MediaPlayer instance
uuid: b376096b-0aed-4ac2-96e5-e30a4eaf742e
---

# Reset or reuse a MediaPlayer instance{#reset-or-reuse-a-mediaplayer-instance}

You can reset, reuse, or release a MediaPlayer instance that you no longer need.

When you reset a MediaPlayer instance, it is returned to its uninitialized IDLE state as defined in MediaPlayerStatus.

This operation is useful in the following cases:

* You want to reuse a `MediaPlayer` instance but need to load a new `MediaResource` (video content) and replace the previous instance.

  Resetting allows you to reuse the `MediaPlayer` instance without the overhead of releasing resources, recreating the `MediaPlayer`, and reallocating resources. The `replaceCurrentItem` and `replaceCurrentResource` methods automatically do these steps for you, without having to call the reset method. 

* When the `MediaPlayer` has an ERROR status and needs to be cleared. 

  >[!IMPORTANT]
  >
  >This is the only way to recover from the ERROR status.

1. Call `reset` to return the `MediaPlayer` instance to its uninitialized state:

   ```
   function reset():void; 
   
   ```

1. Use `MediaPlayer.replaceCurrentItem` or `MediaPlayer.replaceCurrentResource` to load another `MediaResource`.

   >[!TIP]
   >
   >To clear an error, load the same `MediaResource`.

1. When you receive the the `MediaPlaybackStatusChangeEvent.STATUS_CHANGED` with the `PREPARED` status, start the playback.
