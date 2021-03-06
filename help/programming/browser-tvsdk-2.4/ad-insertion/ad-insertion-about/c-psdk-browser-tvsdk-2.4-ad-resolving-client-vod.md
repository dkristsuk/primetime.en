---
description: For video-on-demand (VOD) content, Browser TVSDK inserts ad breaks by splicing the ads in the main content so that the timeline duration increases.
seo-description: For video-on-demand (VOD) content, Browser TVSDK inserts ad breaks by splicing the ads in the main content so that the timeline duration increases.
seo-title: VOD ad resolving and insertion
title: VOD ad resolving and insertion
uuid: 34a30ae5-d553-4c5d-9829-8e5eaa41c104
---

# VOD ad resolving and insertion{#vod-ad-resolving-and-insertion}

For video-on-demand (VOD) content, Browser TVSDK inserts ad breaks by splicing the ads in the main content so that the timeline duration increases.

Before playback, Browser TVSDK resolves known ads, inserts ad breaks in the main content as described by a timeline that is returned from Adobe Primetime ad decisioning, and recomputes the virtual timeline, if necessary.

Browser TVSDK inserts ads in the following ways:

* **Pre-roll**, which is before the content. 
* **Post-roll**, which is after the content.

After playback starts, no additional changes can occur in the content. Ads cannot be:

* Inserted 
* Deleted

  For example, you cannot delete built-in ads from the content to offer an ad-free experience. 
* Replaced

  For example, you cannot replace built-in ads with targeted ads.

