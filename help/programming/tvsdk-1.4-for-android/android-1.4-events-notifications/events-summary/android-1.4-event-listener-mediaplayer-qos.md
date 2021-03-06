---
description: TVSDK dispatches quality of service (QoS) events to notify your application about events that could influence the computation of QoS statistics, such as buffering or seeking.
seo-description: TVSDK dispatches quality of service (QoS) events to notify your application about events that could influence the computation of QoS statistics, such as buffering or seeking.
seo-title: QoS events
title: QoS events
uuid: 27f60cd3-d3fc-4ea3-81df-96d0fe9f7068
---

# QoS events{#qos-events}

TVSDK dispatches quality of service (QoS) events to notify your application about events that could influence the computation of QoS statistics, such as buffering or seeking.

 To be notified about all QoS-related events, register an implementation of `MediaPlayer.QOSEventListener` including the following callbacks:

|  Event  | Meaning  |
|---|---|
| [onBufferComplete](https://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.QOSEventListener.html#onBufferComplete())  | Buffering is complete.  |
| [onBufferStart](https://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.QOSEventListener.html#onBufferStart())  | Buffering has started.  |
| [onLoadInfo](https://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.QOSEventListener.html#onLoadInfo(com.adobe.mediacore.qos.LoadInfo))(loadInfo)  | A fragment has successfully downloaded.  |
|  [onOperationFailed](https://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.QOSEventListener.html)(MediaPlayerNotification. [Warning](https://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerNotification.Warning.html) warning)  | A recoverable error has occurred.  |
| [onSeekComplete](https://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.QOSEventListener.html#onSeekComplete(long))(long adjustedTime)  | Seeking is complete.  |
| [onSeekStart](https://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.QOSEventListener.html#onSeekStart())  | Seeking is starting.  |