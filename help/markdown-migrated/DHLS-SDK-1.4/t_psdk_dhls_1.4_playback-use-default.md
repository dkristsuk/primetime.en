---
description: You can choose to use default ad behaviors.
seo-description: You can choose to use default ad behaviors.
seo-title: Use the default playback behavior
title: Use the default playback behavior
---

# Use the default playback behavior

>1. To use default behaviors:
>    * If you implement your own `codeph  ContentFactory` class, return a new instance of `codeph  DefaultAdPolicySelector` in your implementation of `codeph  doRetrieveAdPolicySelector`.
>      ```
>      public class CustomContentFactory extends ContentFactory { 
>       
>       //... 
>       // your custom code for advertising classes 
>       //... 
>       
>       /** 
>       * @inheritDoc 
>       */ 
>       override protected function 
>       doRetrieveAdPolicySelector(item:MediaPlayerItem):AdPolicySelector { 
>       return new DefaultAdPolicySelector(item); 
>       } 
>      }
>      ```
>      
>    * If you do not have a custom implementation for the `codeph  ContentFactory` class,  uses `codeph  DefaultAdPolicySelector`.
>   
>   