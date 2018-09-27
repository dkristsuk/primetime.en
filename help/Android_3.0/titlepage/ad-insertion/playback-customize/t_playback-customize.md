---
description: You can customize or override ad behaviors.
seo-description: You can customize or override ad behaviors.
seo-title: Set up customized playback
title: Set up customized playback
uuid: d7c5ff2d-9d69-41c0-a0d7-a13b1ca51c12
index: y
internal: n
snippet: y
translate: y
---

# Set up customized playback

You can customize or override ad behaviors.

Before you customize or override ad behaviors, register the ad policy instance with TVSDK. 

* Implement the `AdPolicySelector` interface and all its methods. This option is recommended if you need to override **all** the default ad behaviors. 

* Extend the `DefaultAdPolicySelector` class and provide implementations for only those behaviors that require customization. This option is recommended if you need to override only **some** of the default behaviors. 



To customize ad behaviors: 

1. Implement the `AdPolicySelector` interface and all of its methods.
1. Assign the policy instance to be used by TVSDK through the advertising factory.


   >[!NOTE] {type="attention"}
   >
   >Custom ad policies that are registered at the beginning of playback are cleared when the `MediaPlayer` instance is deallocated. Your application must register a policy selector instance each time a new playback session is created. 
   For example: 
   ```
   java   class CustomContentFactory extends ContentFactory { 
       ... 
       @Override 
       public AdPolicySelector retrieveAdPolicySelector(MediaPlayerItem mediaPlayerItem) { 
           return new CustomAdPolicySelector(mediaPlayerItem); 
       } 
       ... 
   } 
    
   // register the custom content factory with media player 
   MediaPlayerItemConfig config =  new MediaPlayerItemConfig(); 
   config.setAdvertisingFactory(new CustomContentFactory()); 
    
   // this config will should be later passed while loading the resource 
   mediaPlayer.replaceCurrentResource(resource, config);
   ```


1. Implement your customizations.