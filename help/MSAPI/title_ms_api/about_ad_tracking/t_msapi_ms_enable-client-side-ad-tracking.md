---
description: You can enable client-side ad tracking by adding the pttrackingmode and pttrackingversion parameters to your Bootstrap URL request.
seo-description: You can enable client-side ad tracking by adding the pttrackingmode and pttrackingversion parameters to your Bootstrap URL request.
seo-title: Enable client-side ad tracking
title: Enable client-side ad tracking
uuid: d8d86300-cae5-457c-9a9f-84af7d963de9
index: y
internal: n
snippet: y
translate: y
---

# Enable client-side ad tracking

You can enable client-side ad tracking by adding the pttrackingmode and pttrackingversion parameters to your Bootstrap URL request.

With client-side ad tracking enabled, you can also retrieve ad tracking metadata using the Tracking API URL. For more details see  api_notvsdk_ms/notvsdk-query . 

To perform client-side ad tracking, use the Tracking API URL. 

1. Add the following query parameters to the manifest server request URL:

    
    * `pttrackingmode=simple`    
    * `pttrackingversion={format version}`    
    
    
    
For example:
```
http://. . .?. . .&pttrackingmode=simple&pttrackingversion=v1
```