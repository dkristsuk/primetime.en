---
description: You can configure custom tag names in TVSDK globally with the PTSDKConfig class.
seo-description: You can configure custom tag names in TVSDK globally with the PTSDKConfig class.
seo-title: Config class methods for tags
title: Config class methods for tags
uuid: 27f1df0a-bbd3-4d80-820e-b659f2f33069
---

# Config class methods for tags {#config-class-methods-for-tags}

You can configure custom tag names in TVSDK globally with the PTSDKConfig class.

TVSDK applies the global configuration automatically to any media stream that does not specify a stream-specific configuration.

`PTSDKConfig` exposes these methods to manage the custom tags:  

| **Subscribe to specific custom tags** |  |
|---|---|
|  `subscribedTags`  | Retrieves the current list of subscribed tags.  |
| `setSubscribedTags`  | Sets the list of subscribed tags that will be exposed to the application.  |
| **Customize the ad tags used by the default opportunity detector** |
|  `adTags`  | Retrieves the current list of ad tags.  |
|  `setAdTags`  | Sets the list of ad tags that will be used by default opportunity generator.  |


Remember the following:

* The setter methods do not allow the tags parameter to contain null values. 
* The custom tag name must contain the # prefix.

  For example, #EXT-X-ASSET is a correct custom tag name, but EXT-X-ASSET is incorrect. 
* You cannot change the configuration after the media stream has been loaded.