---
seo-title: Primetime DRM on the client
title: Primetime DRM on the client
uuid: 472180ad-6596-4a24-aa51-7909a75a5e10
---

# Primetime DRM on the client{#primetime-drm-on-the-client}

A Primetime TVSDK application that plays protected content must first call Primetime DRM APIs to initiate the workflow for license consumption and protected content playback. In this workflow, Primetime DRM on the client constructs a license request from the metadata of the protected content, then sends it to the Primetime DRM license server.

Before issuing the license request, the client may optionally perform necessary authentication/authorization (depending on your business rules). 
