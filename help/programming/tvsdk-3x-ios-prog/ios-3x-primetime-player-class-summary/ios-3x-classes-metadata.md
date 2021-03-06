---
description: These classes provide metadata for advertising, namespaces, and tracking.
seo-description: These classes provide metadata for advertising, namespaces, and tracking.
seo-title: Metadata classes
title: Metadata classes
uuid: 9cabd1b7-4343-41a1-a3e7-1b61235992db
---

# Metadata classes {#metadata-classes}

These classes provide metadata for advertising, namespaces, and tracking.

|  **Name**  | **Description**  |
|---|---|
| [PTAdMetadata](https://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTAdMetadata.html)  | Class that provides properties that should be configured for resolving ads for a given media item. All the required properties must be set to configure the player for successfully resolving ads.  |
| [PTAuditudeMetadata](https://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTAuditudeMetadata.html)  |Class that extends `PTAdMetadata` specifically for Adobe Primetime ad decisioning. Provides properties to be configured for resolving Adobe Primetime ad decisioning ads for a given media item. You must set all the required properties, including zone ID, media ID, and ad server URL, to configure the player for successfully resolving ads.  |
| [PTMetadata](https://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTMetadata.html)  | Defines the base class for configuring all available metadata for your player and additional objects. |
| [PTTimedMetadata](https://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTTimedMetadata.html)  | Class that represents a custom HLS tag in the stream.  |
| [PTTrackingMetadata](https://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTTrackingMetadata.html)  | Defines a base class for all tracking and analytics related metadata.  |