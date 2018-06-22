---
seo-title: Essential operations of video playback
title: Essential operations of video playback
---

# Essential operations of video playback

The PlaybackManager provides essential operations of HLS streaming:
* Invokes the [`apiname PlaybackManagerEventListener`](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/manager/PlaybackManager.PlaybackManagerEventListener.html), that can respond appropriately to video events.
* Provides playback operation such as play, pause and seek.
* Returns the information about the player such as player status, playback range, and the video live stream.
* Determines if ABR is enabled and sets the ABR and buffer control parameters depending on the supplied configuration data.
* Determines if buffer control is enabled and sets the buffer control parameters depending on the supplied configuration data.
