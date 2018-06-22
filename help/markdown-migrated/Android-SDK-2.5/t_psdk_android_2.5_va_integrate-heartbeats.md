---
description: You can configure your player to track and analyze video use.
seo-description: You can configure your player to track and analyze video use.
seo-title: Initialize and configure video analytics
title: Initialize and configure video analytics
---

# Initialize and configure video analytics

Before activating video tracking (video heartbeats), ensure that you have the following:
* 2.5 for Android.
* Configuration / Initialization Information
<table id="table_3565328ABBEE4605A92EAE1ADE5D6F84"> 
 <tgroup cols="2"> 
  <colspec colnum="1" colname="col1" colwidth="1.00*" /> 
  <colspec colnum="2" colname="col2" colwidth="1.92*" /> 
  <tbody> 
   <tr> 
    <td colname="col1"> <span class="filepath"> ADBMobileConfig.json </span> </td> 
    <td colname="col2"> <p type="important">Note:  This JSON config file name must remain <span class="filepath"> ADBMobileConfig.json </span>. The name and the path of this configuration file cannot be changed. The path to this file must be <span class="filepath"> &lt;source root&gt;/assets </span>. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> AppMeasurement tracking server endpoint </td> 
    <td colname="col2"> The URL of the Adobe Analytics (formerly SiteCatalyst) back-end collection endpoint. </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Video analytics tracking server endpoint </td> 
    <td colname="col2"> The URL of the video analytics back-end collection endpoint. This is where all video heartbeat tracking calls are sent. <p type="tip">Note:  The URL of the visitor tracking server is the same as the URL of the analytics tracking server. For information about implementing the Visitor ID Service, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-target.html" format="html" scope="external"> Implement ID Service </a>. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Account name </td> 
    <td colname="col2"> Also known as the Report Suite ID (RSID). </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Marketing Cloud organization ID </td> 
    <td colname="col2"> A string value required for instantiating the Visitor component. </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

  Contact your Adobe representative for your specific video-tracking account information:
  
  
To configure video tracking in your player:

>1. Confirm that load-time options in the `codeph  ADBMobileConfig.json` resource file are correct.
>   ```
>   { 
>       "version" : "1.1", 
>       "analytics" : { 
>           "rsids" : "adobedevelopment", 
>           "server" : "10.131.129.149:3000", 
>           "charset" : "UTF-8", 
>           "ssl" : false, 
>           "offlineEnabled" : false, 
>           "lifecycleTimeout" : 5, 
>           "batchLimit" : 50, 
>           "privacyDefault" : "optedin", 
>           "poi" : [] 
>       }, 
>    "marketingCloud": { 
>    "org": "ADOBE PROVIDED VALUE" 
>    }, 
>       "target" : { 
>           "clientCode" : "", 
>           "timeout" : 5 
>       }, 
>       "audienceManager" : { 
>           "server" : "" 
>       } 
>   }
>   ```
>   This JSON-formatted configuration file is bundled as a resource with . Your player reads these values only at load time, and the values remain constant while your application runs.
>   
>   To configure load-time options:
>1. Confirm that the `codeph  ADBMobileConfig.json` file contains the appropriate values (provided by Adobe).
>1. Confirm that this file is located in the `codeph  assets/` folder.
>   This folder must be located in the root of your application source tree.
>   
>   
>1. Compile and build your application.
>1. Deploy and run the bundled application.
>   For more information about these AppMeasurement settings, see [ Measuring Video in Adobe Analytics ](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/).
>   
>   
>   
>   
>   
>1. Initialize and configure video heartbeat tracking metadata.
>   >[!IMPORTANT]
>   >
>   >You can stop the video analytics module midstream and reinitialize it again as necessary. Before the module is reinitialized, ensure that the video analytics metadata is also updated to the correct content metadata. To recreate the metadata, repeat the first two steps below (sub-steps**a** and **b**).
>   
>   >1. Create an instance of the Video Analytics metadata.
>   >   This instance contains all of the configuration information that is needed to enable video heartbeat tracking. For example:
>   >   ```java
>   >   private VideoAnalyticsMetadata getVideoAnalyticsTrackingMetadata() { 
>   >       VideoAnalyticsMetadata vaMetadata = new VideoAnalyticsMetadata(); 
>   >     
>   >       vaMetadata.setTrackingServer("example.com"); 
>   >       vaMetadata.setChannel("test-channel"); 
>   >       vaMetadata.setVideoName("myvideo"); 
>   >       vaMetadata.setVideoId("myvideoid"); 
>   >       vaMetadata.setPlayerName("PSDK Player"); 
>   >       vaMetadata.setUseSSL(false); 
>   >       vaMetadata.debugLogging = true; // Set to NO for production deployment. 
>   >       vaMetadata.setEnableChapterTracking(true); 
>   >    // use this API to override the default asset length -1 for live streams 
>   >    vaMetadata.setAssetDuration(SAMPLE_ASSET_DURATION); 
>   >     
>   >       return vaMetadata; 
>   >   }
>   >   ```
>   >   
>   >   
>   >1. Initialize the Video Analytics provider.
>   >   After creating a media player instance, you must create a Video Analytics provider instance and provide the application context to it.
>   >   >[!TIP]
>   >   >
>   >   >Always create a new provider instance for each content playback session and remove the previous reference after you detach the media player instance.
>   >   ```java
>   >   VideoAnalyticsProvider videoAnalyticsProvider = new VideoAnalyticsProvider(appContext); 
>   >   
>   >   ```
>   >   
>   >   
>   >1. Set the Video Analytics metadata on the `codeph  videoAnalyticsProvider` instance.
>   >   ```java
>   >   videoAnalyticsProvider.setVideoAnalyticsMetadata(vaMetadata);
>   >   ```
>   >   
>   >   
>   >1. Attach the media player instance to the `codeph  videoAnalyticsProvider` instance:
>   >   ```java
>   >   videoAnalyticsProvider.attachMediaPlayer(mediaPlayer);
>   >   ```
>   >   
>   >       
>   >   
>   >1. Destroy the Video Analytics provider.
>   >   Before you begin a new content playback session, destroy the previous instance of the video provider. After you receive the content complete event (or notification), wait a few minutes before you destroy the video analytics provider instance. Destroying the instance immediately might interfere with the Video Analytics provider's ability to send a "video complete" ping.
>   >       
>   >       ```java
>   >       if (videoAnalyticsProvider) { 
>   >        videoAnalyticsProvider.detachMediaPlayer(); 
>   >        videoAnalyticsProvider = null; 
>   >       }
>   >       ```
>   >       
>   >   
>   >1. Manually mark the Live/Linear stream as complete.
>   >   If you have various episodes on one live stream, you can manually mark an episode as complete by using the complete API. This ends the video tracking session for the current video episode, and you can start a new tracking session for the next episode.
>   >   >[!TIP]
>   >   >
>   >   >This API is optional and does not work for VOD video tracking.
>   >   
>   >       
>   >       ```java
>   >       if (videoAnalyticsProvider) { 
>   >        videoAnalyticsProvider.trackVideoComplete(); 
>   >       }
>   >       ```
>   >       
>   >   
>   >   
>   
>   