---
description: Browser TVSDK can detect changed playback information in master m3u8 manifests for live streaming and update the playback information while the stream is playing. Browser TVSDK supports a dynamic set of bit rate profiles as the profiles appear or disappear from the master manifest, including non-overlapping profile bit rates between updates.
seo-description: Browser TVSDK can detect changed playback information in master m3u8 manifests for live streaming and update the playback information while the stream is playing. Browser TVSDK supports a dynamic set of bit rate profiles as the profiles appear or disappear from the master manifest, including non-overlapping profile bit rates between updates.
seo-title: Live master-manifest update
title: Live master-manifest update
uuid: 4b918a73-dacf-465a-82d6-404c6bdb01f2
---

# Live master-manifest update{#live-master-manifest-update}

Browser TVSDK can detect changed playback information in master m3u8 manifests for live streaming and update the playback information while the stream is playing. Browser TVSDK supports a dynamic set of bit rate profiles as the profiles appear or disappear from the master manifest, including non-overlapping profile bit rates between updates.

The following features are supported:

* Profile count (increasing or decreasing) 
* Profile bit rates (overlapping or not overlapping) 
* Profiles with URLs on the same (or different) servers 
* Any failover structure

All of the following conditions must be met:

* Stream is live. 
* Both the time and the etag change. 
* All rendition information remains the same (except that URLs may vary). 
* The DRM access information remains the same. 
* Segments are packaged around the same PTS and frame boundaries in a small error range.

