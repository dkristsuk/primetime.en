---
description: These classes describe events that the TVSDK dispatches to your media player in response to various activities.
seo-description: These classes describe events that the TVSDK dispatches to your media player in response to various activities.
seo-title: Events classes
title: Events classes
uuid: 82748fc2-e361-4359-9bcf-0916282d9e49
index: y
internal: n
snippet: y
---

# Events classes{#events-classes}

These classes describe events that the TVSDK dispatches to your media player in response to various activities.

 Package: [com.adobe.mediacore.events](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/package-detail.html) 

|  Name  | Meaning  |
|---|---|
| ` [AdBreakPlaybackEvent](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdBreakPlaybackEvent.html)`  | Class. An ad break started or completed.  |
| ` [AdClickEvent](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdClickEvent.html)`  | Class. The user clicked an ad.  |
| ` [AdPlaybackEvent](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdPlaybackEvent.html)`  | Class. The player played an ad.  |
| ` [BufferEvent](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/BufferEvent.html)`  | Class. The player started or stopped buffering.  |
| ` [CustomAdEvent](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/CustomAdEvent.html)`  | Class. The player displays custom ad loading status and can ignore ads that have errors or are taking too long to load.  |
| ` [DRMMetadataInfoEvent](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/DRMMetadataInfoEvent.html)`  | Class. New DRM metadata is associated with the current item.  |
| ` [LoadInformationEvent](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/LoadInformationEvent.html)`  | Class. Download information is available for the current media stream being played.  |
| ` [MediaPlayerItemEvent](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/MediaPlayerItemEvent.html)`  | Class. A media player item has been created.  |
| ` [MediaPlayerItemLoaderEvent](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/MediaPlayerItemLoaderEvent.html)`  |Class. A load operation has completed. Dispatched by `MediaPlayerItemLoader` to notify its clients.  |
| ` [MediaPlayerStatusChangeEvent](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/MediaPlayerStatusChangeEvent.html)`  | Class. The media player status changed.  |
| ` [MediaPlayerViewEvent](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/MediaPlayerViewEvent.html)`  | Class. The `MediaPlayerView` was clicked.  |
| ` [PlaybackRateEvent](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/PlaybackRateEvent.html)`  | Class. The media player's playback rate changes.  |
| ` [ProfileEvent](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/ProfileEvent.html)`  | Class. The media player’s adaptive bit rate switching algorithm has switched to another profile due to network or machine conditions.  |
| ` [SeekEvent](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/SeekEvent.html)`  | Class. The player started seeking or the seek operation completed.  |
| ` [SizeAvailableEvent](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/SizeAvailableEvent.html)`  | Class. The video size is available.  |
| ` [TimeChangeEvent](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/TimeChangeEvent.html)`  | Class. The media player’s status changed.  |
| ` [TimedMetadataEvent](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/TimedMetadataEvent.html)`  | Class. A timed metadata is processed by the opportunity detector.  |
| ` [TimelineEvent](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/TimelineEvent.html)`  | Class. The media player timeline has changed.  |
