---
description: After you successfully load the MediaResource object, TVSDK creates an instance of the MediaPlayerItem class to provide access to that resource.
seo-description: After you successfully load the MediaResource object, TVSDK creates an instance of the MediaPlayerItem class to provide access to that resource.
seo-title: About the MediaPlayerItem class
title: About the MediaPlayerItem class
uuid: 01feac79-50c6-4d48-aeed-e0a6f2ebb72e
index: y
internal: n
snippet: y
translate: y
---

# About the MediaPlayerItem class

After you successfully load the MediaResource object, TVSDK creates an instance of the MediaPlayerItem class to provide access to that resource.

The `MediaResource` represents a request that is issued by the application layer to the `MediaPlayer` instance to load content. 

The `MediaPlayer` resolves the media resource, loads the associated manifest file, and parses the manifest. This is the asynchronous part of the resource loading process. The `MediaPlayerItem` instance is produced after the resource has been resolved, and this instance is a resolved version of a `MediaResource`. TVSDK provides access to the newly created `MediaPlayerItem` instance through `MediaPlayer.CurrentItem`. 

>[!TIP]
>
>You must wait for the resource to be successfully loaded before accessing the media player item.