---
description: TVSDK dispatches ad-serving events in response to timed metadata operations.
seo-description: TVSDK dispatches ad-serving events in response to timed metadata operations.
seo-title: Ad serving/timed metadata events
title: Ad serving/timed metadata events
uuid: 00d434f8-aeb4-4d82-b401-0238079f61a1
index: y
internal: n
snippet: y
---

# Ad serving/timed metadata events{#ad-serving-timed-metadata-events}

TVSDK dispatches ad-serving events in response to timed metadata operations.

 To be notified about all such related events, register event listeners with the `MediaPlayer` object for the following events. 

|  Event  | Meaning  |
|---|---|
| `TimedMetadataEvent. [TIMED_METADATA_ID3_ADDED](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/TimedMetadataEvent.html#TIMED_METADATA_ID3_ADDED)`  | An ID3 timed metadata was processed.  |
| `TimedMetadataEvent. [TIMED_METADATA_SKIPPED](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/TimedMetadataEvent.html#TIMED_METADATA_SKIPPED)`  | A timed metadata was processed and no opportunity was detected.  |
| `TimedMetadataEvent. [TIMED_METADATA_AVAILABLE](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_2.3/com/adobe/tvsdk/mediacore/events/TimedMetadataEvent.html#TIMED_METADATA_AVAILABLE)`  | Timed metadata is available and no opportunity was detected.  |
| `TimedMetadataEvent. [TIMED_METADATA_IN_BACKGROUND](http://help.stage.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_2.3/com/adobe/tvsdk/mediacore/events/TimedMetadataEvent.html#TIMED_METADATA_IN_BACKGROUND)`  | Timed metadata was processed and no opportunity was detected in the background manifest.  |
