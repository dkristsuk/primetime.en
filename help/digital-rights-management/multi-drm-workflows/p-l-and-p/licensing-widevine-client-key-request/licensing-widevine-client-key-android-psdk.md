---
description: Client code passes data to an Android API.
seo-description: Client code passes data to an Android API.
seo-title: Key request workflow on Android PSDK
title: Key request workflow on Android PSDK
uuid: 575163de-0f96-434d-a3ff-7e114caf72de
---

# Key request workflow on Android PSDK{#key-request-workflow-on-android-psdk}

Client code passes data to an Android API.

On Android, your client code should pass in the license server URL and accompanying license acquisition data using the following API:

```
class DRMManager 
   { 
   ... 
   /* 
   * Set the license server URL and attached request properties that the PSDK should use for the passed in drm type.  
   * 
   * drmType: "com.widevine.alpha" for widevine. "com.microsoft.playready" for playready. 
   * licenseServerURL: self explanatory.  
   * requestProperties: key value pairs to be attached as HTTP headers to all license request sent to the passed in license server URL. Pass in 
   * NULL if none is needed.  
   */ 
   public static void setProtectionData(String drmType, String licenseServerURL,  Map<String, String> requestProperties); 
    }
```

After successfully calling this API, your code can then start content playback the usual way. If the you are using Expressplay, you can either pass the token as part of the license server URL or as a request property and strip out the token from the license server URL.

Some Android devices support both Widevine and PlayReady. On such devices the customer may want to force PSDK to decrypt the content using a particular DRM if the content has multiple DRM headers. This can be done by calling the following API before playback:

```
class MediaPlayer 
   { 
   ... 
    
   /* 
   * drm: pass in "com.widevine.alpha" for widevine or "com.microsoft.playready" for playready 
   * 
   */ 
   public void setDRMScheme(String drm) throws MediaPlayerException 
   }
```

