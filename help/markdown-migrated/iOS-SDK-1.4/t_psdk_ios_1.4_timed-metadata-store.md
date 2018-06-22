---
description: Your application must use the appropriate PTTimedMetadata objects at the appropriate times.
seo-description: Your application must use the appropriate PTTimedMetadata objects at the appropriate times.
seo-title: Store timed metadata objects as they are dispatched
title: Store timed metadata objects as they are dispatched
---

# Store timed metadata objects as they are dispatched

During content parsing, which happens before playback,  identifies subscribed tags and notifies your application about these tags. The time that is associated with each `codeph  PTTimedMetadata` is the absolute time on the playback timeline.

Your application must complete the following tasks:

>1. Keep track of the current playback time.
>   
>1. Match the current playback time to the dispatched `codeph  PTTimedMetadata` objects.
>   
>   
>1. Use the `codeph  PTTimedMetadata` where the start time equals the current playback time.
>   >[!NOTE] {type="restriction"}
>   >
>   >The code below assumes that there is only one`codeph  PTTimedMetadata` instance at a time. If there are multiple instances, the application must save them appropriately in a dictionary. One method is to create an array at a given time and store all instances in that array.
>   
>       
>       `codeph  PTTimedMetadata`
>       `codeph  NSMutableDictionary (timedMetadataCollection)`
>       `codeph  timedMetadata`
>       ```
>       NSMutableDictionary *timedMetadataCollection; 
>        
>       - (void)onMediaPlayerSubscribedTagIdentified:(NSNotification *)notification 
>       { 
>        if (!timedMetadataCollection) 
>        { 
>        timedMetadataCollection = [[NSMutableDictionary alloc] init]; 
>        } 
>        NSDictionary *userInfo = [notification userInfo]; 
>        PTTimedMetadata *timedMetadata = [(PTTimedMetadata *)[userInfo objectForKey:PTTimedMetadataKey] retain]; 
>        if ([timedMetadata.name isEqualToString: @"#EXT-OATCLS-SCTE35"]) 
>        { 
>        NSLog(@"Adding timedMetadata %@ to timedMetadataCollection with time 
>        %f",timedMetadata.name,CMTimeGetSeconds(timedMetadata.time)); 
>        
>        NSNumber *timedMetadataStartTime = [NSNumber numberWithInt:(int)CMTimeGetSeconds(timedMetadata.time)]; 
>        [timedMetadataCollection setObject:timedMetadata forKey:timedMetadataStartTime]; 
>        } 
>        [timedMetadata release]; 
>       }
>       ```
>       
>   
>   