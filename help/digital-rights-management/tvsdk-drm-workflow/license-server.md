---
seo-title: Primetime DRM license server
title: Primetime DRM license server
uuid: 024dd2fe-add5-47b1-8a4d-ec5ec8a97b19
index: y
internal: n
snippet: y
---

# Primetime DRM license server{#primetime-drm-license-server}

The Primetime DRM license server is built from the Primetime DRM Java SDK. This server consumes license requests from clients requesting access to protected content. The server has the ability to parse and manipulate the DRM Policy from within the license request, in order to modify or override the policy before using the policy to generate a license for the requesting client.

In order to deploy a Primetime DRM license server, it must first meet [Adobe’s Compliance and Robustness rules](http://www.adobe.com/content/dam/Adobe/en/products/adobe-access/pdfs/adobe-compliance.pdf) for Primetime DRM. Adobe also offers a hosted Primetime DRM licensing service called [Primetime Cloud DRM](http://help.adobe.com/en_US/primetime/drm/cloud_drm/1.2/cloud-quick-start/index.html#concept-Adobe_Primetime_Cloud_DRM_QuickStart_Guide), that you can use as an alternative to hosting your own license server. 