---
description: By default, when starting playback, VOD media starts at 0 and live media starts at the client live point (DefaultMediaPlayer.LIVE_POINT).
seo-description: By default, when starting playback, VOD media starts at 0 and live media starts at the client live point (DefaultMediaPlayer.LIVE_POINT).
seo-title: Enter a stream at a specific time
title: Enter a stream at a specific time
---

# Enter a stream at a specific time

>1. Pass a position to `codeph  MediaPlayer.prepareToPlay`.
>   considers the given position to be the starting point for the asset. No seek operation is required. If the position is not inside the seekable range,  uses the default position.
>   
>   For example:
>   ```
>   var seekableRange:TimeRange=_mediaPlayer.seekableRange; 
>   if (seekableRange.contains(desiredSeekPosition) { 
>    _mediaPlayer.seek(desiredSeekPosition); 
>   }
>   ```
>   
>   
>   
>   