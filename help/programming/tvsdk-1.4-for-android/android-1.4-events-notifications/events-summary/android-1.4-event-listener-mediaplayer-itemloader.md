---
description: TVSDK dispatches media player item events in response to loading a media item.
seo-description: TVSDK dispatches media player item events in response to loading a media item.
seo-title: Loader events
title: Loader events
uuid: 1b401ff5-4313-4c64-8be9-99bdeb58ba2a
---

# Loader events{#loader-events}

TVSDK dispatches media player item events in response to loading a media item.

These events provide an alternative workflow. You are not required to implement this interface when creating a MediaPlayer. Use this when you want to have a `MediaPlayerItemLoader`.

To be notified about events related to loading a media player resource, register an implementation of `MediaPlayerItemLoader.LoaderListener` including the following events.

|  Event  | Meaning  |
|---|---|
| [onLoadComplete](https://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerItemLoader.LoaderListener.html#onLoadComplete(com.adobe.mediacore.MediaPlayerItem))([mediaPlayerItem](https://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerItem.html) playerItem)  | Media resource loading completed successfully.  |
| [onError](https://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerItemLoader.LoaderListener.html#onError(com.adobe.ave.MediaErrorCode,%20java.lang.String)) | A problem occurred with media resource loading.  |

>[!NOTE]
>
>Also see `onLoadInfo (loadInfo)` under QoS events.

