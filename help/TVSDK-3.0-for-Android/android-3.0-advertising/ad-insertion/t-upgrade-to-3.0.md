---
description: The com.adobe.mediacore.timeline.TimelineMarker interface now contains a new method 
seo-description: The com.adobe.mediacore.timeline.TimelineMarker interface now contains a new method 
seo-title: Upgrading from 2.5.x Lazy Ad Resolving to 3.0.0 Lazy Ad Resolving (API/Workflow changes) 
title: Upgrading from 2.5.x Lazy Ad Resolving to 3.0.0 Lazy Ad Resolving (API/Workflow changes) 
uuid: 091a8155-5688-4536-afbc-f5edd9514a28
index: y
internal: n
snippet: y
---

# Upgrading from 2.5.x Lazy Ad Resolving to 3.0.0 Lazy Ad Resolving (API/Workflow changes):{#upgrading-from-x-lazy-ad-resolving-to-lazy-ad-resolving-api-workflow-changes}

The com.adobe.mediacore.timeline.TimelineMarker interface now contains a new method:

**Placement.Type getPlacementType()**

This method will return a placement type of Placement.Type.PRE_ROLL, Placement.Type.MID_ROLL or Placement.Type.POST_ROLL. If an ad break is unresolved, the `getDuration()`method on the TimelineMarker interface will return 0.

>[!NOTE]
>
>This interface not always cast into the type com.mediacore.timeline.advertising.AdBreakTimelineItem if it has not yet been resolved. It will be able to be casted if the `getDuration()` method of the TimelineMarker is greater than 0.

**Event changes:**

`kEventAdResolutionComplete` is now depreciated and is now triggered immediately after the player enters the PREPARED status. Applications that previously only listened to this event to draw the scrub bar should change this to listen for `kEventTimelineUpdated` only. After individual ad breaks are resolved, a new `kEventTimelineUpdated` event will be dispatched. 