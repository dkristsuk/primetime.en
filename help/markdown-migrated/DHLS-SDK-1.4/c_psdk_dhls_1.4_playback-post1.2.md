---
description: The behavior of media playback is affected by seeking, pausing, fast forward or rewind (trick play mode), and the inclusion of advertising.
seo-description: The behavior of media playback is affected by seeking, pausing, fast forward or rewind (trick play mode), and the inclusion of advertising.
seo-title: Default and customized playback behavior with ads
title: Default and customized playback behavior with ads
---

# Default and customized playback behavior with ads

To override the default behavior, use `codeph AdPolicySelector`.


>[!IMPORTANT]
>
>does not provide a way to disable seeking during ads. Adobe recommends that you configure your application to disable seeking during ads.

The following table describes how  handles ads and ad breaks during playback:

<table id="table_466538B1C2A646B89EB4F9AA111203BE"> 
 <tgroup cols="3">
  <colspec colnum="1" colname="col1" colwidth="*" />
  <colspec colnum="2" colname="col2" colwidth="*" />
  <colspec colnum="3" colname="col3" colwidth="*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry">Video activity </th> 
    <th colname="col2" class="entry">Default 
     <ph conkeyref="phrases/primetime-sdk-name" /> behavior policy </th> 
    <th colname="col3" class="entry">Customization available through <span class="codeph">AdPolicySelector</span> </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1">During normal play, an ad break is encountered. </td> 
    <td colname="col2"> 
     <ul id="ul_10D2638676EA4ADDA718E61BD4FDC1D2"> 
      <li id="li_D5CC30F063934C738971E2E8AF00C137"> For live/linear, plays the ad break, even if the ad break has already been watched. </li> 
      <li id="li_D962C0938DA74186AE99D117E5A74E38">For VOD, plays the ad break and marks the ad break as watched. </li> 
     </ul> </td> 
    <td colname="col3">Specify a different policy for the ad break by using <span class="codeph">selectPolicyForAdBreak</span>. </td> 
   </tr> 
   <tr> 
    <td colname="col1">Your application seeks forward over ad break(s) into main content. </td> 
    <td colname="col2">Plays the last unwatched ad break that was skipped over and resumes playback at the desired seek position when the break(s) playback is complete. </td> 
    <td colname="col3">Select which skipped break to play by using <span class="codeph">selectAdBreaksToPlay</span>. </td> 
   </tr> 
   <tr> 
    <td colname="col1">Your application seeks backward over ad break(s) into main content. </td> 
    <td colname="col2">Skips to the desired seek position without playing ad breaks. </td> 
    <td colname="col3">Select which skipped break to play by using <span class="codeph">selectAdBreaksToPlay</span>.</td> 
   </tr> 
   <tr> 
    <td colname="col1">Your application seeks forward into an ad break. </td> 
    <td colname="col2">Plays from the beginning of the ad in which the seek ended. </td> 
    <td colname="col3">Specify a different ad policy for the ad break and for the specific ad where the seek ended by using <span class="codeph">selectPolicyForSeekIntoAd</span>. </td> 
   </tr> 
   <tr> 
    <td colname="col1">Your application seeks backward into an ad break. </td> 
    <td colname="col2">Plays from the beginning of the ad in which the seek ended. </td> 
    <td colname="col3">Specify a different ad policy for the ad break and for the specific ad in which the seek ended by using <span class="codeph">selectPolicyForSeekIntoAd</span>. </td> 
   </tr> 
   <tr> 
    <td colname="col1">Your application seeks forward or backward over watched ad break(s) into main content. </td> 
    <td colname="col2">If the last ad break skipped has already been watched, skips to the user-selected seek position. </td> 
    <td colname="col3">Select which of the skipped breaks to play using <span class="codeph">selectAdBreaksToPlay</span> and determine which breaks have already been watched by using <span class="codeph">TimeLineItem.watched</span> . <p type="important">Note: By default, 
      <ph conkeyref="phrases/primetime-sdk-name" /> marks an ad break as watched immediately after entering the first ad in the ad break. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1">Your application seeks forward or backward over one or more ad breaks and drops into a watched ad break. </td> 
    <td colname="col2">Skips the ad break and seeks to the position immediately following the ad break. </td> 
    <td colname="col3">Specify a different ad policy for the ad break (with the watched status set to true) and for the specific ad where the seek ended by using <span class="codeph">selectPolicyForSeekIntoAd</span>. </td> 
   </tr> 
   <tr> 
    <td colname="col1">Your application enters trick-play (DVR mode). Play rate can be negative (rewind) or greater than 1 (fast forward). </td> 
    <td colname="col2">Skips all ads during fast forward or rewind, plays the last break skipped after trick play ends, and skips to the user-selected trick play position when that break finishes playback. </td> 
    <td colname="col3">Select which of the skipped breaks to play after trick play ends using <span class="codeph">selectAdBreaksToPlay</span>. </td> 
   </tr> 
   <tr> 
    <td colname="col1">Your application seeks forward over ads that were inserted using custom ad markers. </td> 
    <td colname="col2">Skips to the user-selected seek position. </td> 
    <td colname="col3">For more information, see <a href="t_psdk_dhls_1.4_ui-seek-scrub-bar-display.xml#display-seek-scrub-bar" format="dita" scope="local">Display a seek scrub bar with the current playback position...</a> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>
