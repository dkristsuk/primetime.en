---
description: You can obtain a description of the timeline associated with the currently selected item being played by . This is most useful when your application displays a custom scrub-bar control in which the content sections that correspond to ad content are identified.
seo-description: You can obtain a description of the timeline associated with the currently selected item being played by . This is most useful when your application displays a custom scrub-bar control in which the content sections that correspond to ad content are identified.
seo-title: Inspect the playback timeline
title: Inspect the playback timeline
---

# Inspect the playback timeline

Here is an example implementation as seen in the following screen shot.

>1. Access the `codeph  Timeline` object in the `codeph  MediaPlayer` using the `codeph  getTimeline()` method.
>   The `codeph  Timeline` class encapsulates the information that is related to the contents of the timeline that is associated with the media item that is currently loaded by the `codeph  MediaPlayer` instance. The `codeph  Timeline` class provides access to a read-only view of the underlying timeline. The `codeph  Timeline` class provides a getter method that provides an iterator through a list of `codeph  TimelineMarker` objects.
>   
>   
>   
>1. Iterate through the list of `codeph  TimelineMarkers` and use the returned information to implement your timeline.
>   A `codeph  TimelineMarker` object contains two pieces of information:
>   
>* Position of the marker on the timeline (in milliseconds)
>* Duration of the marker on the timeline (in milliseconds)
>   
>   
>1. Listen for the `codeph  MediaPlayerEvent.TIMELINE_UPDATED` event on the `codeph  MediaPlayer` instance, and implement the `codeph  TimelineUpdatedEventListener.onTimelineUpdated()` callback.
>   The`codeph  Timeline` object can inform your application about changes that might occur in the playback timeline by calling your `codeph  OnTimelineUpdated` listener.
>   
>   