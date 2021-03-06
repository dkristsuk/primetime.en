---
description: TVSDK supports resolving and inserting ads for VOD and live/linear streams.
seo-description: TVSDK supports resolving and inserting ads for VOD and live/linear streams.
seo-title: Primetime ad server metadata
title: Primetime ad server metadata
uuid: 61e224dd-551a-438f-8560-e64915087fef
---

# Enable ads in full-event replay {#section_6016E1DAF03645C8A8388D03C6AB7571}

Full-event replay (FER) is a VOD asset that acts as a live/DVR asset, so your application must take steps to ensure that ads are placed correctly.

For live content, TVSDK uses the metadata/cues in the manifest to determine where to place ads. However, sometimes live/linear content might resemble VOD content. For example, when live content completes, an `EXT-X-ENDLIST` tag is appended to the live manifest. For HLS, the `EXT-X-ENDLIST` tag means that the stream is a VOD stream. TVSDK cannot automatically differentiate this stream from a normal VOD stream to correctly insert ads.

Your application must tell TVSDK whether the content is live or VOD by specifying the `PTAdSignalingMode`.

For a FER stream, the Adobe Primetime ad decisioning server should not provide the list of ad breaks that need to be inserted on the timeline before starting the playback. This is the typical process for VOD content. Instead, by specifying a different signaling mode, TVSDK reads all the cue points from the FER manifest and goes to the ad server for each cue point to request an ad break. This process is similar to live/DVR content.

In addition to each request that is associated with a cue point, TVSDK makes an additional ad request for pre-roll ads.

1. From an external source, such as vCMS, obtain the signaling mode that should be used. 
1. Create the advertising-related metadata. 
1. If the default behavior must be overwritten, specify the `PTAdSignalingMode` by using `PTAdMetadata.signalingMode`.

   The valid values are `PTAdSignalingModeDefault`, `PTAdSignalingModeManifestCues`, and `PTAdSignalingModeServerMap`.

   You must set the ad signaling mode before calling `prepareToPlay`. After TVSDK starts to resolve and place ads on the timeline, changes to the ad signaling mode are ignored. Set the mode when you create the advertising metadata for the resource. 

1. Continue to playback. 

   ```
      PTMetadata *metadata = [[[PTMetadata alloc] init] autorelease]; 
   PTAuditudeMetadata *adMetadata = [[[PTAuditudeMetadata alloc] init] autorelease]; 
   adMetadata.zoneId = your-auditude-zone-id; 
   adMetadata.domain = @"your-auditude-domain"; 
   //adMetadata.enableDVRAds = YES; // FOR LIVE DVR case 
   //adMetadata.signalingMode = PTAdSignalingModeManifestCues;  
   // FOR VOD FER case 
   NSMutableDictionary *targetingParameters = [[[NSMutableDictionary alloc] init] autorelease]; 
   [targetingParameters setValue:@"ipad" forKey:@"device"]; 
   [targetingParameters setValue:@"preroll" forKey:@"AD_OPPORTUNITY_ID"]; 
   adMetadata.targetingParameters = targetingParameters; 
   NSMutableDictionary *customParameters = [[[NSMutableDictionary alloc] init] autorelease]; 
   [customParameters setValue:@"your-media-id" forKey:@"NW_ID"]; 
   [customParameters setValue:@"preroll" forKey:@"AD_OPPORTUNITY_ID"]; 
   adMetadata.customParameters = customParameters; 
   [metadata setMetadata:adMetadata forKey:PTAdResolvingMetadataKey]; 
   
   ```