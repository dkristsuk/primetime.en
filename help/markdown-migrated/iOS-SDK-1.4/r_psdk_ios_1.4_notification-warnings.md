---
---

<a id="section_F25366B6703040E3ADA993C113618F01"></a>

Most warnings contain relevant metadata, for example, the URL of the resource that failed to download. Some notifications contain metadata to specify whether the problem occurred in the main video content, in the alternate audio content, or in an ad.

<table frame="all" colsep="1" rowsep="1" id="table_C24772DF203B4DB2ACE6B475698C4C58"> 
 <tgroup cols="5" colsep="1" rowsep="1" class="FormatA"> 
  <colspec colnum="1" colname="1" colwidth="1.00*" /> 
  <colspec colnum="2" colname="2" colwidth="1.94*" /> 
  <colspec colnum="3" colname="3" colwidth="2.25*" /> 
  <colspec colnum="4" colname="4" colwidth="2.72*" /> 
  <colspec colnum="5" colname="5" colwidth="3.45*" /> 
  <thead> 
   <tr rowsep="1"> 
    <th colname="1" class="entry">Code </th> 
    <th colname="2" class="entry">Name </th> 
    <th colname="3" class="entry">InnerNotification </th> 
    <th colname="4" class="entry">Metadata Keys </th> 
    <th colname="5" class="entry">Comments </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr rowsep="1"> 
    <td namest="1" nameend="5"><b>Ad resolving </b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">201002</span> </td> 
    <td colname="2"><span class="codeph">AD_ASSET_ FAILED_TO_LOAD</span> </td> 
    <td colname="3"> <p>None </p> </td> 
    <td colname="4"><span class="codeph">AD_ASSET, INTERNAL_ERROR</span> </td> 
    <td colname="5"> <p>An error has occurred when trying to load an ad creative. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">201003</span> </td> 
    <td colname="2"><span class="codeph">AD_RESOLVER_ RETURNED_NO_ADS</span> </td> 
    <td colname="3"> <p>None </p> </td> 
    <td colname="4"><span class="codeph">INTERNAL_ERROR, AD_ID,DESCRIPTION</span> </td> 
    <td colname="5"> <p>Ad resolving failed because of an invalid VAST URL or because no ad was returned from the VAST wrapper. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="1" nameend="4"> <p>Note: adID and source (URL) can be retrieved through the PTAdAsset in the notification metadata with the <span class="codeph">AD_ASSET</span> key. </p> </td> 
    <td colname="5"> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="1" nameend="5"><b>Background manifests</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"> 204000 </span> </td> 
    <td colname="2"><span class="codeph">BACKGROUND_MANIFEST_ WARNING</span> </td> 
    <td colname="3"> <p>None </p> </td> 
    <td colname="4"><span class="codeph">BACKGROUND_MANIFEST_ WARNING_ERROR</span> <span class="codeph">BACKGROUND_MANIFEST_ WARNING_NAME</span> <span class="codeph">DESCRIPTION</span> </td> 
    <td colname="5"> <p> Error in background manifest download. Any issue in updating the background manifest is dispatched as a 
      <ph conkeyref="phrases/primetime-sdk-name" /> warning and does not cause the playback to stop. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"> 204001 </span> </td> 
    <td colname="2"><span class="codeph">INVALID_SEEK_ WARNING</span> </td> 
    <td colname="3"> <p>None </p> </td> 
    <td colname="4"><span class="codeph">DESCRIPTION</span> </td> 
    <td colname="5"> <p> </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="1" nameend="5"><b>TimeRangeCollection </b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">210000 </span> </td> 
    <td colname="2"><span class="codeph">UNDEFINED_ TIME_RANGES </span> </td> 
    <td colname="3"> <p>None </p> </td> 
    <td colname="4">None </td> 
    <td colname="5"> The ad signaling mode is defined as custom ranges but there are not any ranges defined. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">210001 </span> </td> 
    <td colname="2"><span class="codeph">INVALID_TIME_ RANGES </span> </td> 
    <td colname="3"> <p>None </p> </td> 
    <td colname="4"><span class="codeph">DESCRIPTION </span> </td> 
    <td colname="5"> <p> One or more time ranges are invalid and will be ignored or modified. </p> <p> DESCRIPTION is a string containing description of the invalid ranges. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="1" nameend="5"><b>iOS specific </b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">270000 </span> </td> 
    <td colname="2"><span class="codeph">PLAYER_NOT_READY </span> </td> 
    <td colname="3"> <p>None </p> </td> 
    <td colname="4"><span class="codeph">DESCRIPTION </span> </td> 
    <td colname="5"> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">270001 </span> </td> 
    <td colname="2"><span class="codeph">AD_NOT_INSERTED </span> </td> 
    <td colname="3"> <p>None </p> </td> 
    <td colname="4"> <p>None </p> </td> 
    <td colname="5"> <p>AD was not inserted on the stream. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">270002 </span> </td> 
    <td colname="2"><span class="codeph">AD_HLS_AUDIOONLY_MISSING </span> </td> 
    <td colname="3"><span class="codeph">AD_NOT_INSERTED </span> </td> 
    <td colname="4"> <p>None </p> </td> 
    <td colname="5"> <p>Ad does not contain Audio Only Stream </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">270003 </span> </td> 
    <td colname="2"><span class="codeph">AD_HLS_MATCHING_BITRATE_MISSING </span> </td> 
    <td colname="3"><span class="codeph">AD_NOT_INSERTED </span> </td> 
    <td colname="4"> <p>None </p> </td> 
    <td colname="5"> <p>No matching ad stream found for content's current bitrate. </p> <p>&nbsp; </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">270005 </span> </td> 
    <td colname="2"><span class="codeph">AVASSET_FAILED_TO_CREATE </span> </td> 
    <td colname="3"><span class="codeph">PLAYBACK_ERROR </span> </td> 
    <td colname="4"> <p>None </p> </td> 
    <td colname="5"> <p>Error at creating the AVAsset. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">270006 </span> </td> 
    <td colname="2"><span class="codeph">SITECATALYST_WARNING </span> </td> 
    <td colname="3"> <p>None </p> </td> 
    <td colname="4"><span class="codeph">DESCRIPTION </span> </td> 
    <td colname="5"> <p>Warning: See sitecatalyst warning description. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">270007 </span> </td> 
    <td colname="2"><span class="codeph">NETWORK_ERROR </span> </td> 
    <td colname="3"> <p>None </p> </td> 
    <td colname="4"><span class="codeph">URL </span> </td> 
    <td colname="5"> <p>Error getting data from the network. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">270002</span> </td> 
    <td colname="2"><span class="codeph">AD_HLS_AUDIOONLY_MISSING</span> </td> 
    <td colname="3"> <p>None </p> </td> 
    <td colname="4"><span class="codeph">AD_ASSET</span> </td> 
    <td colname="5"> <p>The audio for this ad cannot be heard because it is missing </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">270003</span> </td> 
    <td colname="2"><span class="codeph">AD_HLS_MATCHING_BITRATE_MISSING</span> </td> 
    <td colname="3"> <p>None </p> </td> 
    <td colname="4"><span class="codeph">AD_ASSET</span> </td> 
    <td colname="5"> <p>The matching bitrate is missing. </p> <p>&nbsp; </p>
     <!-- workaround for PDF having too much negative kerning in column 2  --> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>
