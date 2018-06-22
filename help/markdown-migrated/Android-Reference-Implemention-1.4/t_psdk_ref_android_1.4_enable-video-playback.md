---
description: Create a PlaybackManager that handles the HLS stream setup and playback operation. No other configuration is required.
seo-description: Create a PlaybackManager that handles the HLS stream setup and playback operation. No other configuration is required.
seo-title: Enable video playback
title: Enable video playback
---

# Enable video playback

>1. Create the media player object by making sure the following code exists in `filepath  PlayerFragment.java`:
>   ```java
>   private MediaPlayer createMediaPlayer() { 
>    MediaPlayer mediaPlayer = DefaultMediaPlayer.create(getActivity().getApplicationContext()); 
>    return mediaPlayer;
>   ```
>   <!-- I've duplicated this information. It also exists in the PlayerFragment section, just before the Feature manager section. I figured that I should have it here as well, in case they jump directly to this section. -->
>   
>1. Create the playback manager through the `codeph  ManagerFactory`:
>   ```java
>   playbackManager = ManagerFactory.getPlaybackManager(config, mediaPlayer);
>   ```
>   
>   
>1. Implement the `codeph  PlaybackManagerEventListener` in the `codeph  PlayerFragment` to handle the playback events:
>   ```java
>   private final PlaybackManagerEventListener playbackManagerEventListener = 
>    new PlaybackManagerEventListener()
>   ```
>   
>   
>1. Register the event listener in the `codeph  PlayerFragment`:
>   ```
>   playbackManager.addEventListener(playbackManagerEventListener);
>   ```
>   
>   
>1. Set up the video resource:
>   ```
>   playbackManager.setupVideo(url, adsManager);
>   ```
>   
>   
>1. Set up the control bar operations in the `codeph  PlayerFragment`:
>   ```
>   controlBar.pressPlay() { 
>    playbackManager.play(); 
>   }
>   ```
>   
>   
>   