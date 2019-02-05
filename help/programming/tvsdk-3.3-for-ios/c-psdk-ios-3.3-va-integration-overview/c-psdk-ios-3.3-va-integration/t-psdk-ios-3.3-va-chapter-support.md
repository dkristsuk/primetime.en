---
description: null
seo-description: null
seo-title: Implement chapter support
title: Implement chapter support
uuid: b0e5ef1c-6568-4901-9ac7-261df71a0110
index: y
internal: n
snippet: y
---

# Implement chapter support {#implement-chapter-support}

You can define and track chapters for video tracking in a TVSDK-based application in the following ways:

* Default chapters, which are managed internally by TVSDK.

  A chapter is defined as the time between each ad break. For example, the time between a pre-roll ad break and the first mid-roll is defined as the first chapter. 
* Custom chapters, which are managed by the application and are based on CMS data or another way that the application uses to define chapters.

1. Define and track default or custom chapters.

   ```
   // First, enable chapter tracking by setting the boolean 'enableChapterTracking' to true: 
    
       vaTrackingMetadata.enableChapterTracking = YES; 
     
   // For custom chapter definitions, provide an array of chapters through the metadata:  
   // For example, 3 chapters of 60 second duration each: 
    
       NSMutableArray *chapters = [[[NSMutableArray alloc] init] autorelease]; 
         
       int chapterDuration = 60; 
       for (int i = 0; i < 3; i++) 
       { 
           PTVideoAnalyticsChapterData *chapterData =  
             [[[PTVideoAnalyticsChapterData alloc] init] autorelease]; 
           chapterData.name = [NSString stringWithFormat:@"chapter_%d", (i+1)]; 
           chapterData.range =  
             CMTimeRangeMake(CMTimeMakeWithSeconds(i * chapterDuration, 10000),  
             CMTimeMakeWithSeconds(chapterDuration, 10000)); 
             
           [chapters addObject:chapterData]; 
       } 
         
       vaTrackingMetadata.chapters = chapters; 
     
   // For default chapters, the application must not set custom chapters on the tracking metadata  
   // and simply enable chapters to be tracked by setting the boolean value as defined above.
   ```