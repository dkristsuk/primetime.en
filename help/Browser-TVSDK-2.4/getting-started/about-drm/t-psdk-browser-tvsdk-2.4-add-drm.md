---
description: null
seo-description: null
seo-title: Add Digital Rights Management
title: Add Digital Rights Management
uuid: fc10cb81-aea5-4c6a-9e3b-1b55762484de
index: y
internal: n
snippet: y
---

# Add Digital Rights Management{#add-digital-rights-management}

1. Add the `DRMMetadataInfoAvailableEvent` to get the `DRMMetadata`.

   ```js
   player.addEventListener(AdobePSDK.PSDKEventType.DRM_METADATA_INFO_AVAILABLE, onDRMMetadataInfoAvaialble);
   ```

1. Implement the `onDRMMetadataInfoAvailable` section above the line in step 1.

   ```js
   var onDRMMetadataInfoAvaialble = function(event) { 
    var drmMetadataInfo = event.drmMetadataInfo; 
    var drmMetadata = null; 
    
    if(drmMetadataInfo) { 
     drmMetadata = drmMetadataInfo.drmMetadata; 
    } 
    
    drmManager.acquireLicense(drmMetadata, null, null); 
   };
   ```

1. Create the DRMManager in the setupVideo method.

   ```js
   var drmManager = player.drmManager;
   ```

1. Create the protection data for Widevine and PlayReady by copying the following sample:

   ```js
   var protectionData = { 
     "com.widevine.alpha":{ 
       "serverURL":"https://wv.service.expressplay.com/hms/wv/rights/? 
                    ExpressPlayToken=[YOUR_EXPRESSPLAY_TOKEN]"  
     }, 
    
     "com.microsoft.playready":{ 
       "serverURL":"http://pr.test.expressplay.com/playready/RightsManager.asmx? 
                    ExpressPlayToken=[YOUR_EXPRESSPLAY_TOKEN]", 
         "httpRequestHeaders":{ 
       } 
     } 
   };
   ```

1. Add the protection data to the drmManager.

   ```js
   drmManager.setProtectionData(protectionData);
   ```

1. Change the resource URL to a DASH test stream.

   >[!TIP]
   >
   >Ensure that you update the resource type, because this is now DASH.

   ```js
   var resourceUrl = "http://ptdemos.com/videos/dashdrm/stream.mpd"; 
   var resourceType = AdobePSDK.MediaResourceType.DASH;
   ```

1. Test your configuration.