---
description: The status of the media player determines which actions are legal.
seo-description: The status of the media player determines which actions are legal.
seo-title: Lifecycle and statuses of the MediaPlayer object
title: Lifecycle and statuses of the MediaPlayer object
---

# Lifecycle and statuses of the MediaPlayer object

For working with media player statuses:
* You can retrieve the current status of the `codeph  MediaPlayer` object with `codeph  MediaPlayer.getStatus()`.
* The list of statuses is defined in the [ MediaPlayerStatus ](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_2.5/com/adobe/mediacore/MediaPlayerStatus.html) enum.

Status-transition diagram for the lifecycle of a `codeph  MediaPlayer` instance:

<table id="table_82757A0043EB4AACA474E6B30326A6B7"> 
 <tgroup cols="2"> 
  <colspec colnum="1" colname="col1" colwidth="1.00*" /> 
  <colspec colnum="2" colname="col2" colwidth="2.74*" /> 
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Status </th> 
    <th colname="col2" class="entry"> Occurs when </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> IDLE </td> 
    <td colname="col2"> <p>The media player's initial status. The player is created and is waiting for you to specify a media player item. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> INITIALIZING </td> 
    <td colname="col2"> <p>Your application calls <span class="codeph"> MediaPlayer.replaceCurrentItem() </span>. </p> <p>The media player item is loading. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> INITIALIZED </td> 
    <td colname="col2"> <p>TVSDK successfully set the media-player item. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PREPARING </td> 
    <td colname="col2"> <p>Your application calls <span class="codeph"> MediaPlayer.prepareToPlay() </span>. The media player is loading the media player item and any associated resources. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PREPARED </td> 
    <td colname="col2"> <p>TVSDK has prepared the media stream and has attempted to perform ad resolving and ad insertion (if enabled). The content is prepared and ads have been inserted in the timeline, or the the ad procedure failed. </p> <p>Buffering or playback can begin. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> PLAYING/PAUSED </td> 
    <td colname="col2"> <p>As the application plays and pauses the media, the media player moves between these statuses. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> SUSPENDED </td> 
    <td colname="col2"> <p>If the application navigates away from the playback, shuts down the device, or switches applications while the player is playing or paused, the media player is suspended and resources are released. </p> <p>Calling <span class="codeph"> MediaPlayer.restore() </span> returns the player to the status the player was in before it was SUSPENDED. The exception is if the player is SEEKING when suspended is called, the player is PAUSED and then SUSPENDED. </p> <p type="important">Note:  <p>Remember the following information: 
       <ul id="ul_1B21668994D1474AAA0BE839E0D69B00"> 
        <li id="li_08459A3AB03C45588D73FA162C27A56C">The <span class="codeph"> MediaPlayer </span> automatically calls <span class="codeph"> suspend </span> only when the surface object that is used by the <span class="codeph"> MediaPlayerView </span> is destroyed. </li> 
        <li id="li_B9926AA2E7B9441490F37D24AE2678A1">The <span class="codeph"> MediaPlayer </span> automatically calls <span class="codeph"> restore() </span> only when a new surface object that is used by the <span class="codeph"> MediaPlayerView </span> is created. </li> 
       </ul> </p> </p> <p>If you always want playback to be paused when the MediaPlayer is restored, have your application call <span class="codeph"> MediaPlayer.pause() </span> in the Android Activity's <span class="codeph"> onPause() </span> method. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> COMPLETE </td> 
    <td colname="col2"> <p>The player has reached the end of the stream, and playback has stopped. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> RELEASED </td> 
    <td colname="col2"> <p>Your application released the media player, which also releases any associated resources. You can no longer use this instance. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> ERROR </td> 
    <td colname="col2"> <p>An error occurred during the process. An error also might affect what the application can do next. For more information, see <a href="t_psdk_android_2.5_error-handling-set-up.xml#set-up-error-handling" format="dita" scope="local"> Set up error handling </a>. </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

The following table provides details about the lifecycle and statuses of the media player:

>[!TIP]
>
>You can use the status to provide feedback on the process, or example, a spinner while waiting for the next status change, or take the next steps in playing the media, such as waiting for the appropriate status before calling the next method.
For example:
```java
mediaPlayer.addEventListener(MediaPlayerEvent STATUS_CHANGED, new StatusChangeEventListener() { 
 @Override 
 public void onStatusChanged(MediaPlayerStatusChangeEvent event) { 
 switch(event.getStatus()) { 
 case INITIALIZED: 
 mediaPlayer.prepareToPlay(); 
 break; 
 case PREPARING: 
 showBufferingSpinner(); 
 break; 
 case PREPARED: 
 hideBufferingSpinner(); 
 mediaPlayer.play(); 
 break; 
 ... 
 } 
 ... 
 } 
}); 

```
