---
description: Event handlers allow TVSDK to respond to events. When an event occurs, TVSDK's event mechanism calls your registered event handler and passes the event information to the handler.
seo-description: Event handlers allow TVSDK to respond to events. When an event occurs, TVSDK's event mechanism calls your registered event handler and passes the event information to the handler.
seo-title: Implement event listeners and callbacks
title: Implement event listeners and callbacks
uuid: d9f49c77-f833-4bef-a8f2-6a6e364f5d8a
index: y
internal: n
snippet: y
---

# Implement event listeners and callbacks{#implement-event-listeners-and-callbacks}

Event handlers allow TVSDK to respond to events. When an event occurs, TVSDK's event mechanism calls your registered event handler and passes the event information to the handler.

The Flash Runtime provides a generic events mechanism, which the TVSDK also uses and defines a series of custom events. Your application must implement event listeners for TVSDK events that affect your application.

For a complete list of the events for video analytics, see [Track Core Video Playback](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/c_vhl_track-core-vid-playback.html). 

1. Determine for which events your application must listen.

    * **Required events**: Listen for all playback events.     
    
      >[!IMPORTANT]
      >
      >The playback event `MediaPlayerStatusChangeEvent.STATUS_CHANGE` provides the player status, including errors. Any of the states might affect your player's next step.

    * **Other events**: Optional, depending on your application.

      For example, if you incorporate advertising in your playback, listen for all `AdBreakPlaybackEvent` and `AdPlaybackEvent` events.

1. Implement event listeners for each event.

   TVSDK returns parameter values to your event-listener callbacks. These values, provide relevant information about the event that you can use in your listeners to perform appropriate actions.

   The `Event` class lists all the callback interfaces. Each interface displays the parameters that are returned for that interface.

   For example: 

   ```
   public function MediaPlayerStatusChangeEvent(type:String,  
                   bubbles:Boolean = false,  
                   cancelable:Boolean = false,  
                   status:String = null,  
                   error:MediaError = null) 
   
   ```

1. Register your callback listeners with the `MediaPlayer` object by using `MediaPlayer.addEventListener`.

   `MediaPlayer` extends `flash.events.IEventDispatcher`, which is part of the Flash player core files and includes the functions `addEventListener` and `removeEventListener`. 

   ```
   mediaPlayer.addEventListener( 
     MediaPlayerStatusChangeEvent.STATUS_CHANGED,  
     onStatusChanged);
   ```
