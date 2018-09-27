---
description: When TVSDK encounters a broken VMAP in an ad server response, it dispatches an 1109 (NETWORK_AD_URL_FAILED) error.
keywords: 1109;NETWORK_AD_URL_FAILED;broken VMAP
seo-description: When TVSDK encounters a broken VMAP in an ad server response, it dispatches an 1109 (NETWORK_AD_URL_FAILED) error.
seo-title: Client error handling for broken VMAP
title: Client error handling for broken VMAP
uuid: cedf9169-1db4-47e9-bbe5-5534b87b6026
index: y
internal: n
snippet: y
translate: y
---

# Client error handling for broken VMAP

When TVSDK encounters a broken VMAP in an ad server response, it dispatches an 1109 (NETWORK_AD_URL_FAILED) error.

Depending upon the nature of the ad server response, and upon your ad loading settings, your player could receive different numbers of 1109 errors when TVSDK encounters a broken VMAP in an ad server response. 

Let's consider a scenario in which the ad server response points to VMAP XML. Let's also say that the ad server response has four available ad slots, each of which points to the same VMAP. Finally, let's say that this VMAP is broken. 

In this scenario, if lazy ad resolving is enabled ( [t_enable-lazy-ad-resolving.xml](../../../titlepage/ad-insertion/c_lazy-ad-resolving/t_enable-lazy-ad-resolving.md)), TVSDK will dispatch two 1109 errors (not one as might be expected): one error is dispatched on each parsing pass over the timeline. This is because when lazy ad resolving is enabled, TVSDK parses the ads in 2 passes: the first pass happens just before the content playback starts for pre-roll ads, and the second pass happens after playback starts, for mid-roll and post-roll ads. 

>[!NOTE]
>
>In this scenario, if you disable lazy ad resolving, TVSDK will fire only one 1109 error (only one parsing pass).