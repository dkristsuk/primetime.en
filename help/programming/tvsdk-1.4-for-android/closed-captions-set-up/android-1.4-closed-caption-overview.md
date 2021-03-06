---
description: Closed captioning displays the audio portion of a video as text on the screen when the sound is inaudible or the viewer is hard of hearing.
seo-description: Closed captioning displays the audio portion of a video as text on the screen when the sound is inaudible or the viewer is hard of hearing.
seo-title: Select a current caption track from among available tracks
title: Select a current caption track from among available tracks
uuid: 637a70c9-9bef-4b13-8b1f-62f22f983e80
---

# Overview {#work-with-closed-captions}

Closed captioning displays the audio portion of a video as text on the screen when the sound is inaudible or the viewer is hard of hearing.

Closed captions are typically in the same language as the audio and also display background sounds as text, but subtitles are typically in a different language and do not include background sounds.

TVSDK supports rendering these formats:

* 608 and 708 closed captioning, when delivered as part of the video transport stream over HLS as data packets in MPEG-2 video streams. 
* WebVTT caption files, which are referenced from the M3U8 manifest files as defined in the HLS specifications. They are automatically available as closed-caption tracks in the Primetime player.

You can:

* Select an available caption track to be the current track and listen for events that indicate additional available tracks. 
* Switch closed captioning on or off (visible or not visible) by using the `MediaPlayer` interface. 
* Select styling options that dictate how closed captions are rendered by the underlying video engine. Use the `MediaPlayerItem` interface to select formats such as the font or font color.
