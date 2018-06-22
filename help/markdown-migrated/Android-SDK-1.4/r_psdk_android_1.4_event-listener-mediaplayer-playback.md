---
---

>To be notified about all playback-related events, register an implementation of `codeph MediaPlayer.PlaybackEventListener`, including the following event callbacks.
>
>
<table frame="all" colsep="1" rowsep="1"> 
 <tgroup cols="2" colsep="1" rowsep="1" class="FormatA"> 
  <colspec colnum="1" colname="1" colwidth="1*" /> 
  <colspec colnum="2" colname="2" colwidth="2*" /> 
  <thead> 
   <tr rowsep="1"> 
    <th colname="1" class="entry">Event </th> 
    <th colname="2" class="entry">Meaning </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr rowsep="1"> 
    <td namest="1" nameend="2"><b>Playback</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.PlaybackEventListener.html#onPlayComplete()" format="html" scope="external">onPlayComplete</a> </td> 
    <td colname="2">The end of a media source has been reached. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.PlaybackEventListener.html#onPlayStart()" format="html" scope="external">onPlayStart</a> </td> 
    <td colname="2">Playback of a media source has started. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.PlaybackEventListener.html#onRateSelected(float)" format="html" scope="external">onRateSelected</a> (float rate) </td> 
    <td colname="2">The user or 
     <ph conkeyref="phrases/primetime-sdk-name" /> has selected a new playback rate, such as fast forward, rewind, or resume playing at a normal speed. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.PlaybackEventListener.html#onRatePlaying(float)" format="html" scope="external">onRatePlaying</a> (float rate) </td> 
    <td colname="2"> A new playback rate is visible on the screen. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="1" nameend="2"><b>Media</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.PlaybackEventListener.html#onPrepared()" format="html" scope="external">onPrepared</a> </td> 
    <td colname="2">The media player has successfully prepared the media. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.PlaybackEventListener.html#onSizeAvailable(long,%20long)" format="html" scope="external">onSizeAvailable</a> (long height, long width) </td> 
    <td colname="2">The size of the media is available. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="1" nameend="2"><b>Media Player</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.PlaybackEventListener.html#onStateChanged(com.adobe.mediacore.MediaPlayer.PlayerState,com.adobe.mediacore.MediaPlayerNotification)" format="html" scope="local">onStateChanged</a> (<a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.PlayerState.html" format="html" scope="external">MediaPlayer.PlayerState</a> state, <a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerNotification.html" format="html" scope="external">MediaPlayerNotification</a> notification) </td> 
    <td colname="2">The state of the media player has changed. Your application should handle errors in this callback. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.PlaybackEventListener.html#onProfileChanged(long,%20long)" format="html" scope="external">onProfileChanged</a> (long profile, long time) </td> 
    <td colname="2"> The media player’s current profile has changed. Use the <span class="codeph">Profile</span> property to get the new profile that is being played. Use the <span class="codeph">time</span> property to get the time when this event occurred. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="1" nameend="2"><b>MediaplayerItem</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.PlaybackEventListener.html#onUpdated()" format="html" scope="external">onUpdated</a> </td> 
    <td colname="2">The media player has successfully updated the media in either of these cases: 
     <ul> 
      <li>When a manifest refresh occurs for a live asset.</li> 
      <li>When a VOD or live asset has closed captioning and activity is first discovered for a closed captioning track. </li> 
     </ul> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="1" nameend="2"><b>Manifest and Timeline</b></td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.PlaybackEventListener.html#onTimedMetadata(com.adobe.mediacore.metadata.TimedMetadata)" format="html" scope="external">onTimedMetadata</a> (<a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/metadata/TimedMetadata.html" format="html" scope="external">TimedMetadata</a> timedMetadata) </td> 
    <td colname="2">A new timed metadata is discovered in the manifest. </td> 
   </tr> 
   <tr rowsep="0"> 
    <td colname="1"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.PlaybackEventListener.html#onTimelineUpdated()" format="html" scope="external">onTimelineUpdated</a> </td> 
    <td colname="2">The media player has added or removed ads, so it has an updated timeline. <p>The manifest refreshed for a live asset and old ad breaks were removed from the timeline or new ad opportunities (cue points) were discovered. The media player tries to resolve and place any new ads on the timeline. </p><p> Use this event to check whether the timeline has any updates (VOD does not change during playback). You can then retrieve the timeline using <a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.html#getTimeline()" format="html" scope="external">MediaPlayer.getTimeline</a>. </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

>