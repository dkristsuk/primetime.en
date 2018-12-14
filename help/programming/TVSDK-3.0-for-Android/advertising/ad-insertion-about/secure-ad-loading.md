---
seo-title: Secure Ad loading over HTTPS
title: Secure Ad loading over HTTPS
uuid: 988965e0-e9b3-4add-acab-4fc64cec0dab
index: y
internal: n
snippet: y
---

# Secure Ad loading over HTTPS{#secure-ad-loading-over-https}

Adobe Primetime provides an option to request first call to the Primetime ad server and CRS related calls over HTTPS.

The feature is not enabled by default. Use the following to enable secure ad loading.

```
AuditudeSettings auditudeSettings = new AuditudeSettings(); 
auditudeSettings. getForceHttpsConfiguration().setAdServerCalls(true);
```
