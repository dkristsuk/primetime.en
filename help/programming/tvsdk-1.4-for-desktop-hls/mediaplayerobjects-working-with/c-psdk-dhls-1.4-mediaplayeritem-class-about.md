---
description: The MediaPlayer object represents your media player. A MediaPlayerItem represents audio or video on your player.
seo-description: The MediaPlayer object represents your media player. A MediaPlayerItem represents audio or video on your player.
seo-title: About the MediaPlayerItem class
title: About the MediaPlayerItem class
uuid: 531dd1a6-d72c-4ae3-9c3f-2f1d854245c5
---

# About the MediaPlayerItem class{#about-the-mediaplayeritem-class}

The MediaPlayer object represents your media player. A MediaPlayerItem represents audio or video on your player.

<!--<a id="section_01BC89E5C5A94D0A95EF9D29FBCE758A"></a>-->

After a media resource is successfully loaded, TVSDK creates an instance of the `MediaPlayerItem` class to provide access to that resource.

The `MediaResource` represents a request that is issued by the application layer to the `MediaPlayer` instance to load content.

The `MediaPlayer` resolves the media resource, loads the associated manifest file, and parses the manifest. This is the asynchronous part of the resource loading process. The `MediaPlayerItem` instance is produced after the resource has been resolved, and this instance is a resolved version of a `MediaResource`. TVSDK provides access to the newly created `MediaPlayerItem` instance through `MediaPlayer.currentItem`.

>[!TIP]
>
>You must wait for the resource to be successfully loaded before accessing the media player item.

