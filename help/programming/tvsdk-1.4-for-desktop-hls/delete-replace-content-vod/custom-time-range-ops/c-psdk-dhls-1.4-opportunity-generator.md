---
description: null
seo-description: null
seo-title: Opportunity Generator
title: Opportunity Generator
uuid: 26f4dcab-6c6b-4d27-a073-017673bf098f
---

# Opportunity Generatorr{#opportunity-generator}

```
if (resource.metadata != null) { 
 // push in the CustomRangeResolver before other resolvers 
    if (resource.metadata.containsKey(DefaultMetadataKeys.CUSTOM_DELETE_RANGES_METADATA_KEY) 
        result.push(new CustomRangeResolver()); 
    else if (resource.metadata.containsKey(DefaultMetadataKeys.CUSTOM_REPLACE_RANGES_METADATA_KEY)) 
        result.push(new CustomRangeResolver()); 
    if (resource.metadata.containsKey(DefaultMetadataKeys.CUSTOM_AD_MARKERS_METADATA_KEY)) { 
        result.push(new CustomAdResolver());    // no ad insertion with mark ranges 
    } 
    else if (resource.metadata.containsKey(DefaultMetadataKeys.AUDITUDE_METADATA_KEY)) { 
        if (_auditudeResolver == null) { 
              _auditudeResolver = new AuditudeResolver(); 
        } 
        result.push(_auditudeResolver); 
    } 
    else if (resource.metadata.containsKey(DefaultMetadataKeys.JSON_METADATA_KEY)) { 
        result.push(new MetadataResolver()); 
    } 
}
```