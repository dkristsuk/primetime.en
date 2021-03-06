---
description: The MediaPlayer object represents your media player. A MediaPlayerItem represents audio or video on your player.
seo-description: The MediaPlayer object represents your media player. A MediaPlayerItem represents audio or video on your player.
seo-title: About the MediaPlayerItem class
title: About the MediaPlayerItem class
uuid: d7f65edf-4693-4b1e-bae0-46fadce98751
---

# About the MediaPlayerItem class{#about-the-mediaplayeritem-class}

The MediaPlayer object represents your media player. A MediaPlayerItem represents audio or video on your player.

After a media resource is successfully loaded, TVSDK creates an instance of the `MediaPlayerItem` class to provide access to that resource.

The `MediaResource` represents a request that is issued by the application layer to the `MediaPlayer` instance to load content.

The `MediaPlayer` resolves the media resource, loads the associated manifest file, and parses the manifest. This is the asynchronous part of the resource loading process. The `MediaPlayerItem` instance is produced after the resource has been resolved, and this instance is a resolved version of a `MediaResource`. TVSDK provides access to the newly created `MediaPlayerItem` instance through `MediaPlayer.CurrentItem`

>[!TIP]
>
>You must wait for the resource to be successfully loaded before accessing the media player item.

