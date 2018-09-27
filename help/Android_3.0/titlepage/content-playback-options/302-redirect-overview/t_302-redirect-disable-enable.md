---
description: Use the useRedirectedUrl property to turn 302 redirect on (true) or off (false).
seo-description: Use the useRedirectedUrl property to turn 302 redirect on (true) or off (false).
seo-title: Disable or enable 302 redirect optimization
title: Disable or enable 302 redirect optimization
uuid: bbef4eae-dd15-45ae-9d5f-7ed96c1b302e
index: y
internal: n
snippet: y
translate: y
---

# Disable or enable 302 redirect optimization

Use the useRedirectedUrl property to turn 302 redirect on (true) or off (false).

For example:
```
java// Set useRedirectedUrl property to false 
NetworkConfiguration networkConfiguration = new NetworkConfiguration(); 
networkConfiguration.setUseRedirectedUrl(false); 
 
//Set NetworkConfiguration on MediaPlayerItemConfig 
MediaPlayerItemConfig config = new MediaPlayerItemConfig (); 
config.setNetworkConfiguration(networkConfiguration); 
 
//Use this config when loading the MediaPlayerItem or calling replaceCurrentResource
```