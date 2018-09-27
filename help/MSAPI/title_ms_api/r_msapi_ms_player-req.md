---
description: All video players must provide capabilities that the manifest server relies on to insert ads and to enable ad tracking.
seo-description: All video players must provide capabilities that the manifest server relies on to insert ads and to enable ad tracking.
seo-title: Video player requirements
title: Video player requirements
uuid: 87cccece-56e8-498d-9750-5e4665dde3ba
index: y
internal: n
snippet: y
translate: y
---

# Video player requirements

All video players must provide capabilities that the manifest server relies on to insert ads and to enable ad tracking.


>To use the Primetime ad insertion API, a video player must satisfy the following: 
>
>* Can track playhead position as content is played back.>
>* Can request tracking URLs at the times specified.>
>* Runs on a device platform that supports HLS v3 or later, including: >
>    * PTS discontinuities as marked by `EXT-X-DISCONTINUITY` tags>    
>    * `EXT-X-DISCONTINUITY-SEQUENCE`>    
>    * `EXT-X-PROGRAM-DATE-TIME`>    
>    * `EXT-X-START`>    
>    
>    
>
>* Runs on a platform that supports HTTP redirects and parsing JSON.>
>* Runs on a platform that supports CORS.>
>
>