---
---

<a id="section_D29404228F5E4B818642CBA6A0D39546"></a>

Most errors contain relevant metadata, for example, the URL of the resource that failed to download. Some notifications contain metadata to specify whether the problem occurred in the main video content, in the alternate audio content, or in an ad.

<table frame="all" colsep="1" rowsep="1" id="table_8B61210A406A45ACBE37FC29729DDE22"> 
 <tgroup cols="5" colsep="1" rowsep="1" class="FormatA"> 
  <colspec colnum="1" colname="1" colwidth="1.00*" /> 
  <colspec colnum="2" colname="2" colwidth="1.43*" /> 
  <colspec colnum="3" colname="3" colwidth="2.04*" /> 
  <colspec colnum="4" colname="4" colwidth="1.55*" /> 
  <colspec colnum="5" colname="5" colwidth="1.72*" /> 
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
    <td namest="1" nameend="5"><b>Playback</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">101000 </span> </td> 
    <td colname="2"><span class="codeph">PLAYBACK_ERROR </span> </td> 
    <td colname="3">None</td> 
    <td colname="4"><span class="codeph">DESCRIPTION</span> </td> 
    <td colname="5"> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">101004 </span> </td> 
    <td colname="2"><span class="codeph">CONTENT_ERROR</span> </td> 
    <td colname="3"><span class="codeph">DOWNLOAD_ERROR</span></td> 
    <td colname="4"> </td> 
    <td colname="5">An Error has occurred while downloading a fragment or segment(both video and audio). </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">101008 </span> </td> 
    <td colname="2"><span class="codeph">SEEK_ERROR </span> </td> 
    <td colname="3">None </td> 
    <td colname="4"><span class="codeph">NATIVE_ERROR_CODE </span><span class="codeph">DESIRED_SEEK_POSITION </span><span class="codeph">DESIRED_SEEK_PERIOD </span> </td> 
    <td colname="5">An error has occurred while performing a seek operation. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">101009 </span> </td> 
    <td colname="2"><span class="codeph">PAUSE_ERROR </span> </td> 
    <td colname="3">None </td> 
    <td colname="4"><span class="codeph">DESCRIPTION</span> </td> 
    <td colname="5">An error has occurred while performing a pause operation. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">101102 </span> </td> 
    <td colname="2"><span class="codeph">PERIOD_INFO_ERROR </span> </td> 
    <td colname="3">None </td> 
    <td colname="4"><span class="codeph">DESCRIPTION </span> </td> 
    <td colname="5">An error has occurred while retrieving information about a content period. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">101103 </span> </td> 
    <td colname="2"><span class="codeph">RETRIEVE_TIME_ERROR </span> </td> 
    <td colname="3">None </td> 
    <td colname="4"><span class="codeph">DESCRIPTION </span> </td> 
    <td colname="5">An error has occurred while attempting to retrieve the playback position. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">101104 </span> </td> 
    <td colname="2"><span class="codeph">GET_QOS_DATA_ERROR </span> </td> 
    <td colname="3">None </td> 
    <td colname="4"><span class="codeph">DESCRIPTION </span> </td> 
    <td colname="5">An error has occurred while attempting to retrieve the QOS information. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">101200 </span> </td> 
    <td colname="2"><span class="codeph">DOWNLOAD_ERROR </span> </td> 
    <td colname="3"> None </td> 
    <td colname="4"><span class="codeph">URL </span> </td> 
    <td colname="5">An error has occurred while attempting to download data. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="1" nameend="5"><b>Invalid resource </b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">102100 </span> </td> 
    <td colname="2"><span class="codeph">RESOURCE_LOAD_ERROR </span> </td> 
    <td colname="3"> None </td> 
    <td colname="4"><span class="codeph">DESCRIPTION </span><span class="codeph">RESOURCE </span> </td> 
    <td colname="5">An error has occurred while loading a resource item. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">102101 </span> </td> 
    <td colname="2"><span class="codeph">RESOURCE_PLACEMENT_ FAILED </span> </td> 
    <td colname="3"> None </td> 
    <td colname="4"><span class="codeph">CONTENT_ID </span> </td> 
    <td colname="5">An error has occurred while placing a resource on the playback timeline.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="1" nameend="5"><b>Ad processing </b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">104000 </span> </td> 
    <td colname="2"><span class="codeph">AD_RESOLVER_FAIL </span> </td> 
    <td colname="3"><span class="codeph">AD_METADATA _INVALID </span><span class="codeph">AD_RESOLVER_INITIALIZATION_FAIL </span><span class="codeph">AD_RESOLVER_RESOLVE_FAIL </span><span class="codeph">AD_RESOLVER_SERVER_UNREACHABLE </span> </td> 
    <td colname="4"> None </td> 
    <td colname="5"> None </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">104001 </span> </td> 
    <td colname="2"><span class="codeph">AD_RESOLVER_METADATA_ INVALID </span> </td> 
    <td colname="3"> <p>None</p> </td> 
    <td colname="4"><span class="codeph">DESCRIPTION</span> </td> 
    <td colname="5">Ad resolving failed due to invalid ad-metadata format. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">104003 </span> </td> 
    <td colname="2"><span class="codeph">AD_RESOLVER_RESOLVE_ FAIL </span> </td> 
    <td colname="3"> None </td> 
    <td colname="4"><span class="codeph">NATIVE_ERROR_CODE </span> </td> 
    <td colname="5">Ad plugin failed to resolve ads. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">104005 </span> </td> 
    <td colname="2"><span class="codeph">AD_INSERTION_FAIL </span> </td> 
    <td colname="3">None</td> 
    <td colname="4"><span class="codeph">PROPOSED_AD_BREAK</span></td> 
    <td colname="5">Ad resolving phase has failed. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="1" nameend="5"><b>Native</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">106000 </span> </td> 
    <td colname="2"><span class="codeph">NATIVE_ERROR </span> </td> 
    <td colname="3">None </td> 
    <td colname="4"> <span class="codeph">NATIVE_ERROR_CODE </span> <span class="codeph">NATIVE_ERROR_NAME </span> <span class="codeph">DESCRIPTION </span> <span class="codeph">DESCRIPTION</span> <p><b>DRM details:</b> </p> <span class="codeph">DRM_ERROR_STRING</span> <span class="codeph">NATIVE_SUBERROR_CODE</span> </td> 
    <td colname="5"> <p>The low-level AVE library issued an error. </p> <p>See <a href="http://help.adobe.com/en_US/primetime/psdk/android/index.html#PSDKs-concept-Details_for_the_NATIVEERROR_notification" format="html" scope="external">Details for the NATIVE_ERROR notifications</a> for information about the values for these metadata keys. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">106001 </span> </td> 
    <td colname="2"><span class="codeph">ENGINE_CREATION_ ERROR </span> </td> 
    <td colname="3"> None </td> 
    <td colname="4"><span class="codeph">DESCRIPTION </span> </td> 
    <td colname="5">An error has occurred while instantiating the AVE low-level library. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">106002 </span> </td> 
    <td colname="2"><span class="codeph">ENGINE_RELEASE_ ERROR </span> </td> 
    <td colname="3"> None </td> 
    <td colname="4"><span class="codeph">DESCRIPTION </span> </td> 
    <td colname="5">An error has occurred while releasing the AVE low-level library. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">106003 </span> </td> 
    <td colname="2"><span class="codeph">ENGINE_RESOURCES_ RELEASE_ERROR </span> </td> 
    <td colname="3"> None </td> 
    <td colname="4"><span class="codeph">DESCRIPTION </span> </td> 
    <td colname="5">An error has occurred while releasing the GPU resources utilised by the AVE library. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">106004 </span> </td> 
    <td colname="2"><span class="codeph">ENGINE_RESET_ERROR </span> </td> 
    <td colname="3"> None </td> 
    <td colname="4"><span class="codeph">DESCRIPTION </span> </td> 
    <td colname="5">An error has occurred while resetting the AVE library. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">106005 </span> </td> 
    <td colname="2"><span class="codeph">ENGINE_SET_ VIEW_ERROR </span> </td> 
    <td colname="3"> None </td> 
    <td colname="4"><span class="codeph">DESCRIPTION</span> </td> 
    <td colname="5">An error has occurred while attaching a view to the AVE library. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="1" nameend="5"><b>Configuration</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">107000 </span> </td> 
    <td colname="2"><span class="codeph">SET_VOLUME_ERROR </span> </td> 
    <td colname="3"> None </td> 
    <td colname="4"><span class="codeph">DESCRIPTION VOLUME </span> </td> 
    <td colname="5">An error has occurred while attempting to set the volume level. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">107001 </span> </td> 
    <td colname="2"><span class="codeph">SET_BUFFER_TIME_ ERROR </span> </td> 
    <td colname="3"> None </td> 
    <td colname="4"><span class="codeph">DESCRIPTION </span><span class="codeph">PLAY_BUFFER_TIME </span> </td> 
    <td colname="5">An error has occurred while attempting to change the buffering parameters. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">107002 </span> </td> 
    <td colname="2"><span class="codeph">SET_CC_VISIBILITY_ ERROR </span> </td> 
    <td colname="3"> None </td> 
    <td colname="4"><span class="codeph">DESCRIPTION</span> </td> 
    <td colname="5">An error has occurred while attempting to change the visibility of the CC tracks. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">107003 </span> </td> 
    <td colname="2"><span class="codeph">SET_CC_STYLING_ ERROR </span> </td> 
    <td colname="3"> None </td> 
    <td colname="4"><span class="codeph">DESCRIPTION</span> </td> 
    <td colname="5">An error has occurred while attempting to change the styling options for the CC tracks. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">107004 </span> </td> 
    <td colname="2"><span class="codeph">SET_ABR_PARAMETERS_ ERROR </span> </td> 
    <td colname="3"> None </td> 
    <td colname="4"><span class="codeph">DESCRIPTION </span> </td> 
    <td colname="5">An error has occurred while attempting to change the ABR control parameters. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">107005 </span> </td> 
    <td colname="2"><span class="codeph">SET_BUFFER_ PARAMETERS_ERROR </span> </td> 
    <td colname="3"> None </td> 
    <td colname="4"><span class="codeph">DESCRIPTION </span><span class="codeph">INITIAL_BUFFER_TIME </span><span class="codeph">PLAY_BUFFER_TIME </span> </td> 
    <td colname="5">An error has occurred while attempting to change the buffering control parameters. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="1" nameend="5"><b>Alternate audio</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">109000 </span> </td> 
    <td colname="2"><span class="codeph">AUDIO_TRACK_ERROR </span> </td> 
    <td colname="3"><span class="codeph">DOWNLOAD_ERROR </span> </td> 
    <td colname="4"><span class="codeph">AUDIO_TRACK_NAME </span><span class="codeph">AUDIO_TRACK_LANGUAGE </span> </td> 
    <td colname="5">An error related to an audio track occurred. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="1" nameend="5"><b>Generic</b> </td> 
   </tr> 
   <tr rowsep="0"> 
    <td colname="1"><span class="codeph">199999 </span> </td> 
    <td colname="2"><span class="codeph">GENERIC_ERROR</span> </td> 
    <td colname="3"> None </td> 
    <td colname="4"> None </td> 
    <td colname="5">Marks a generic error event. Not actually issued by 
     <ph conkeyref="phrases/primetime-sdk-name" />. This is only a marker for the end of the range of numerical codes corresponding to 
     <ph conkeyref="phrases/primetime-sdk-name" /> error events. </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>
