---
description: If you use the default configuration, there is nothing else you need to do to enable or configure billing. If you obtained different configuration parameters from your Adobe Enablement representative, use the PTBillingMetricsConfiguration class to set these parameters up before initializing the media player.
seo-description: If you use the default configuration, there is nothing else you need to do to enable or configure billing. If you obtained different configuration parameters from your Adobe Enablement representative, use the PTBillingMetricsConfiguration class to set these parameters up before initializing the media player.
seo-title: Configure billing metrics
title: Configure billing metrics
---

# Configure billing metrics

Most customers should use the default configuration.

>[!IMPORTANT]
>
>The configuration you set remains in effect for the life of the media player. Once you initialize the media player, you cannot change the configuration.
To configure billing metrics:

>1. Enter the following code sample.
>   ```
>   PTBillingMetricsConfiguration *billingConfig = [[[PTBillingMetricsConfiguration alloc] init] autorelease]; 
>   billingConfig.enabled = YES; 
>   billingConfig.stdVODBillableDurationMinutes = 60.0; 
>   billingConfig.proVODBillableDurationMinutes = 30.0; 
>   billingConfig.liveBillableDurationMinutes = 15.0; 
>    
>   // metadata is the PTMetadata instance set on PTMediaPlayerItem 
>   [metadata setMetadata:billingConfig forKey:PTBillingMetricsConfigurationMetadataKey];
>   ```
>   
>   
>   