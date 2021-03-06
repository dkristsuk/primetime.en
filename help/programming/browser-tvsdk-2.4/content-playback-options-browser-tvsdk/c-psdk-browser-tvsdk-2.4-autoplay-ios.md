---
description: null
seo-description: null
seo-title: Autoplay on iOS
title: Autoplay on iOS
uuid: d15bad24-be50-49e5-90f4-68dbda96fb6d
---

# Autoplay on iOS{#autoplay-on-ios}

 The implementation of the volume API of AdobePSDK.MediaPlayer allows autoplaying content on devices running iOS version 10 or above. iOS allows autoplay only when the volume is muted. When the volume is set to zero, the API sets the `muted` property of the video tag to `true`, otherwise the `muted` property is set to `false`. The `play` API starts the playback without any user interaction or user gesture.

For autoplay on iPhone, additionally set the `playsInline` property of the `video` tag to `true`. 

```
videoDiv.getElementsByTagName('video')[0].playsInline = true;
```

>[!NOTE]
>
>Use of `playsInline` property starts the playback without the fullscreen mode.

