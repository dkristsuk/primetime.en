---
description: To receive notifications about tags in the manifest, listen for AdobePSDK.TimedMetadataEvent.
seo-description: To receive notifications about tags in the manifest, listen for AdobePSDK.TimedMetadataEvent.
seo-title: Add listeners for timed-metadata notifications
title: Add listeners for timed-metadata notifications
uuid: 59adb7f1-d026-42cc-9600-cf7789441c1c
index: y
internal: n
snippet: y
---

# Add listeners for timed-metadata notifications{#add-listeners-for-timed-metadata-notifications}

To receive notifications about tags in the manifest, listen for AdobePSDK.TimedMetadataEvent.

When a new `TimedMetadata` object is created, the MediaPlayer dispatches `AdobePSDK.TimedMetadataEvent`. 

1. Implement the appropriate listeners.

   ```js
   function onTimedMetadataEvent(event) { 
       var timedMetadata = event.timedMetadata; 
       // process the timed metadata collection 
       } 
   
   ```

1. Register the event listeners.

   ```js
   player.addEventListener(AdobePSDK.PSDKEventType.TIMED_METADATA_AVAILABLE, onTimedMetadataEvent);
   ```

ID3 metadata is dispatched through the same `Events.TimedMetadataEvent`. You can use the `timedMetadata.type` property to distinguish between TAG and ID3.
