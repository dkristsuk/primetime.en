---
description: null
seo-description: null
seo-title: Configure usage model demo mode
title: Configure usage model demo mode
uuid: f818c7fc-e88f-4fa4-926e-08a1337b28d3
---

# Configure usage model demo mode{#configure-usage-model-demo-mode}

Before the Reference Implementation server can issue licenses for the usage model demo, you must configure the server to specify how licenses are generated for each of the four usage models. This means you need to specify a DRM policy for each usage model. The Reference Implementation includes the following sample DRM policies in the [!DNL Reference Implementation/Server/Reference Implementation Server/resources/] directory:

* `dto-policy.pol` - (Download-To-Own)
* `vod-policy.pol` - (Rental/Video-On-Demand)
* `sub-policy.pol` - (Subscription)
* `ad-policy.pol` - (Ad-funded)

>[!NOTE]
>
>You can substitute these sample policies with your own DRM policies.

1. Set these properties in [!DNL flashaccess-refimpl.properties] to specify the DRM policy that you plan to apply to each usage model:

   ```
   # DRM Policy file name for Download To Own usage 
   RefImpl.UsageModelDemo.Policy.DTO=dto-policy.pol 
   # DRM Policy file name for Rental usage 
   RefImpl.UsageModelDemo.Policy.VOD=vod-policy.pol 
   # DRM Policy file name for Subscription usage 
   RefImpl.UsageModelDemo.Policy.Subscribe=sub-policy.pol 
   # DRM Policy file name for Ad Supported (free) usage 
   RefImpl.UsageModelDemo.Policy.Free=ad-policy.pol
   ```

1. Copy your sample policy files to the directory you specify in the `config.resourcesDirectory` property in [!DNL flashaccess-refimpl.properties].
