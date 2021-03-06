---
seo-title: Out-of-band licenses
title: Out-of-band licenses
uuid: 43397ce5-6c52-429d-b7fa-fa8c91cf9742
---

# Out-of-band licenses {#out-of-band-licenses}

Using Primetime DRM, you can implement a workflow in which clients obtain pre-generated licenses out-of-band, and therefore eliminate the need to deploy a license server. To support this workflow, an option indicating that no license server is available should be specified at packaging time. This prevents the client from attempting to request a license for this content from a license server.

Content that indicates the non-availability of a license server can only be played on Primetime DRM clients version 3.0 or later. Older clients need to upgrade to play this content. 
