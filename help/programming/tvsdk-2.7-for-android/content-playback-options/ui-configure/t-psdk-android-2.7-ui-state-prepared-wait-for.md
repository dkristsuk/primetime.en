---
description: Before you can use most of the TVSDK player methods, the player must be in a valid status.
seo-description: Before you can use most of the TVSDK player methods, the player must be in a valid status.
seo-title: Wait for a valid status
title: Wait for a valid status
uuid: ffa63ad6-84d3-4eb2-aa99-026418d86528
---

# Wait for a valid state {#wait-for-a-valid-state}

With TVSDK, you can control the basic playback experience for live and video on demand (VOD). TVSDK provides methods and properties on the player instance that you can use to configure the player user interface.

Before you can use most of the TVSDK player methods, the player must be in a valid status.

 Waiting for the player to be in the correct status ensures that the media resource has successfully loaded. If the player is not in at least the required status, many player methods throw `MediaPlayerException`.

The required status is usually PREPARED. When this occurs, the callback routine for `StatusChangeEventListener.onStatusChanged()` executes. 

1. To confirm that the status is `PREPARED`, check `MediaPlayer.MediaPlayerStatus`.
