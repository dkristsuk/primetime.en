---
description: Remove TimeRanges between begin and end in localTime from the timeline.
seo-description: Remove TimeRanges between begin and end in localTime from the timeline.
seo-title: Delete ranges with Primetime ad decisioning ad
title: Delete ranges with Primetime ad decisioning ad
uuid: efd36a2f-db61-434a-bc2a-50a866f44b33
---

# Delete ranges with Primetime ad decisioning ad{#delete-ranges-with-primetime-ad-decisioning-ad}

Remove TimeRanges between begin and end in localTime from the timeline.

  Delete ranges with an  Phrase ad.

   ```
   {   
       "properties": [],
       "stream": {
           "manifests": [ {
               "url": "https://d398890tia84ty.cloudfront.net/e2e-vod/cloudfront_vod_hls_tos_30fps.m3u8",
               "type": "hls"
           } ],
   
           "metadata": {
               "time-ranges": {
                   "type": "delete",
                   "time-range-list": [ {
                       "begin": 0,
                       "end": 20000
                   },
                   {
                       "begin": 69000,
                       "end": 99000
                   },
                   {
                       "begin": 251000,
                       "end": 281000
                   },
                   {
                       "begin": 514000,
                       "end": 544000
                   } ]
   
               },
               "ad": {
                   "targeting": [ {
                       "value": "MulAdsAvail12346",
                       "key": "osmfKeyMulAdsAvail12346"
                   } ],
                   "domain": "sandbox2.auditude.com",
                   "mediaid": "psdk_000105",
                   "zoneid": "121781"
               }     
           }
       },   
       "title": "VOD - DELETE TimeRange with Adobe Primetime ad decisioningxm-replace_text Phrase Ads",
       "thumbnail": {
           "large": "https://example.com",
           "small": "https://example.com"
       },
       "type": "vod",
       "id": "vod_003"
   }
   
   ```

