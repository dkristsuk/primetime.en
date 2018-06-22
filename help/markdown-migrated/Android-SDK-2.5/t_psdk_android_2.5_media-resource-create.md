---
description: The MediaResource class represents the content to be loaded by the MediaPlayer instance.
seo-description: The MediaResource class represents the content to be loaded by the MediaPlayer instance.
seo-title: Create a media resource
title: Create a media resource
---

# Create a media resource

>1. Create a `codeph  MediaResource` by passing information about the media to the `codeph  MediaResource` constructor.
<table id="table_22886D6770FB45E99D35D0B90E6CC302"> 
 <tgroup cols="2"> 
  <colspec colnum="1" colname="col1" colwidth="1*" /> 
  <colspec colnum="2" colname="col2" colwidth="4*" /> 
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Constructor Parameter </th> 
    <th colname="col2" class="entry"> Description </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <span class="codeph"> url </span> </td> 
    <td colname="col2"> A string representing the URL of the manifest/playlist of the media. </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <span class="codeph"> type </span> </td> 
    <td colname="col2"> One of the following members of the <span class="codeph"> MediaResource.Type </span> enum, corresponding to the indicated file type: 
     <ul id="ul_C286ED3C31364B858A1C9AF3356E9282"> 
      <li id="li_25B24EF76D8849DE8764539F25E435FA"> <span class="codeph"> HLS </span> - M3U8 </li> 
      <li id="li_1344A41B434D49229E392F1AAF9ECA81"> <span class="codeph"> ISOBMFF </span> - ISO base media file format (MP4) </li> 
      <li id="li_92392073B7334916B06B16570C51AC91"> <span class="codeph"> DASH </span> - MPEG-DASH media presentation description (MPD) </li> 
     </ul> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <span class="codeph"> metadata </span> </td> 
    <td colname="col2"> An instance of the <span class="codeph"> Metadata </span> class (a dictionary-like structure), which might contain additional information about the content that is about to be loaded, such as alternate or ad content to place inside the main content. If using advertising, set up <span class="codeph"> AuditudeSettings </span> before using this constructor (see <a keyref="ad-insertion-metadata"></a>). </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

>   The `codeph  MediaResource` constructor requires the following parameters:
>   
>   >[!IMPORTANT]
>   >
>   >supports playback for only specific types of content. If you attempt to load any other type of content, dispatches an error event.
>   >For MP4 video-on-demand (VOD) content,  does not support trick play, adaptive bit rate (ABR) streaming, ad insertion, closed captions, or DRM.
>   >
>   >The following code creates a `codeph  MediaResource` instance:
>   >```java
>   >// To do: Create metadata here 
>   >MediaResource res = new MediaResource( 
>   > "http://www.example.com/video/some-video.m3u8", 
>   > MediaResource.Type.HLS, 
>   > metadata);
>   >```
>   >
>   >
>   At any time after this step, you can use `codeph  MediaResource` accessors (getters) to examine the resource's type, URL, and metadata.
>   
>   
>   
>1. Load the media resource using one of the following options:
>   
>* The MediaPlayer instance.
>* `codeph  MediaPlayerItemLoader`
>  For more information, see [ Load a media resource using MediaPlayerItemLoader ](t_psdk_android_2.5_media-resource-load-using-mediaplayeritemloader.md#use-mediaplayeritemloader).
>  
>  
>   
>   >[!IMPORTANT]
>   >
>   >Do not load the media resource on a background thread. Most operations need to run on the main thread, and running them on a background thread can cause the operation to throw an error and exit.
>   
>   
>   