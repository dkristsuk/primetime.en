---
description: To display banner ads, you need to create banner instances and allow to listen for ad-related events.
seo-description: To display banner ads, you need to create banner instances and allow to listen for ad-related events.
seo-title: Display banner ads
title: Display banner ads
---

# Display banner ads

provides a list of companion banner ads that are associated with a linear ad through the `codeph  AdPlaybackEvent.AD_STARTED` event event.

Manifests can specify companion banner ads by:
* An HTML snippet
* The URL of an iFrame page
* The URL of a static image or an Adobe Flash SWF file

For each companion ad,  indicates which types are available for your application.

>1. Add a listener for the `codeph  AdPlaybackEvent.AD_STARTED` event that does the following:
>   >1. Clears existing ads in the banner instance.
>   >   
>   >1. Gets the list of companion ads from `codeph  Ad.companionAssets`.
>   >   
>   >1. If the list of companion ads is not empty, iterate over the list for banner instances.
>   >   Each banner instance ( an`codeph  AdBannerAsset`) contains information, such as width, height, resource type (html, iframe, or static), and data that is required to display the companion banner.
>   >   
>   >1. If a video ad has no companion ads booked with it, the list of companion assets contains no data for that video ad.
>   >   To show a standalone display ad, add the logic to your script to run a normal DFP (DoubleClick for Publishers) display ad tag in the appropriate banner instance.
>   >   
>   >1. Sends the banner information to a function on your page  that displays the banners in an appropriate location.
>   >   This is usually a `codeph  div`, and your function uses the `codeph  div ID` to display the banner. For example:
>   >   
>   >   Add the event listener:
>   >   ```js
>   >   _player.addEventListener(AdobePSDK.PSDKEventType.AD_STARTED, onAdStarted);
>   >   ```
>   >   
>   >   Implement the listener handler:
>   >   ```js
>   >   private function onAdStarted(event:AdPlaybackEvent):void { 
>   >    // check if there are any companion banner 
>   >    if (event.ad &amp;&amp; event.ad.companionAssets 
>   >    &amp;&amp; event.ad.companionAssets.length &gt; 0) { 
>   >    for each (var banner:AdBannerAsset in event.ad.companionAssets) { 
>   >    if (ExternalInterface.available) { 
>   >    //-- call the java script that will handle the banner display. 
>   >    ExternalInterface.call('addBanner', banner.resourceType, 
>   >    banner.width, banner.height, banner.bannerData); 
>   >    } 
>   >    } 
>   >    } 
>   >    //... 
>   >   }
>   >   ```
>   >   
>   >   Example of JavaScript to handle the display:
>   >   ```js
>   >   function addBanner(resourceType, width, height, data) { 
>   >    console.log(resourceType + "," + width + "," + height); 
>   >    
>   >   //Assume an html element on the page with id like 'banner300x250' 
>   >    var bannerDiv = document.getElementById('banner' + width + 
>   >    'x' + height); 
>   >    if (bannerDiv != null) { 
>   >    if (resourceType == "html") { // for html resource 
>   >    bannerDiv.innerHTML = data; 
>   >    } 
>   >    else if (resourceType == "iframe") { // for iframe resource 
>   >    bannerDiv.innerHTML = "&lt;iframe src='" + data + 
>   >    "' width='100%' height='100%'&gt;&lt;/iframe&gt;"; 
>   >    } 
>   >    } 
>   >   }
>   >   ```
>   >   
>   >   
>   >   
>   >   
>   
>   