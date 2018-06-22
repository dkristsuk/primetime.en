---
description: The feature managers serve as wrappers around the library.
seo-description: The feature managers serve as wrappers around the library.
seo-title: Reference implementation structure
title: Reference implementation structure
---

# Reference implementation structure

In Java, classes are structured in a hierarchy. For example, all the UI-related code under `codeph com.adobe.primetime.reference.ui` and all the feature managers are under `codeph com.adobe.primetime.reference.manager`.

<table id="table_228CB6BB38DF4D60BD28D14ED800FED8"> 
 <tgroup cols="2"> 
  <colspec colnum="1" colname="col1" colwidth="1.00*" /> 
  <colspec colnum="2" colname="col2" colwidth="1.35*" /> 
  <thead> 
   <tr> 
    <th colname="col1" class="entry">Package </th> 
    <th colname="col2" class="entry">Description </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"><a href="http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/PrimetimeReference.html" format="html" scope="external">com.adobe.primetime.reference</a> </td> 
    <td colname="col2">This class extends <span class="codeph">android.app.Application</span>. </td> 
   </tr> 
   <tr> 
    <td colname="col1"><a href="http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/advertising/package-summary.html" format="html" scope="external">com.adobe.primetime.reference.advertising</a> </td> 
    <td colname="col2">Contains code for custom ads. </td> 
   </tr> 
   <tr> 
    <td colname="col1"><a href="http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/package-summary.html" format="html" scope="external">com.adobe.primetime.reference.config</a> </td> 
    <td colname="col2">Contains the interface code required for configuring the feature managers. </td> 
   </tr> 
   <tr> 
    <td colname="col1"><a href="http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/drm/package-summary.html" format="html" scope="external">com.adobe.primetime.reference.drm</a> </td> 
    <td colname="col2">Contains helper classes for DRM. </td> 
   </tr> 
   <tr> 
    <td colname="col1"><a href="http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/feeds/package-summary.html" format="html" scope="external">com.adobe.primetime.reference.feeds</a> </td> 
    <td colname="col2">The adapters and item adapters for interface, platform, and reference information. Also includes the <span class="codeph">FeedAdapterFactory</span>, <span class="codeph">ContentRenditionInfo</span>, and <span class="codeph">XMLParserHelper</span> code. </td> 
   </tr> 
   <tr> 
    <td colname="col1"><a href="http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/logging/package-summary.html" format="html" scope="external">com.adobe.primetime.reference.logging</a> </td> 
    <td colname="col2">Provides classes for logging locally and remotely. </td> 
   </tr> 
   <tr> 
    <td colname="col1"><a href="http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/manager/package-summary.html" format="html" scope="external">com.adobe.primetime.reference.manager</a> </td> 
    <td colname="col2">This is where you can find the feature managers as well as the <span class="codeph">ManagerFactory</span>. For optional features that you can enable or disable, there are two feature managers: 
     <ul id="ul_DB976A6E05494E10B57CE07E816FCE79"> 
      <li id="li_0A4F951B8F4743EFA6350FFADFFFCD57">One feature manager that is the name of the feature, for example, <span class="codeph">CCManager</span>. This feature manager is turned off and provides the default off behavior. </li> 
      <li id="li_FA7B8BBBD3AD468F9A7397B23CBB9361">One feature manager that has On appended to the feature manager name, for example, <span class="codeph">CCManagerOn</span>. This feature manager provides sample code for the enabled feature. </li> 
     </ul> </td> 
   </tr> 
   <tr> 
    <td colname="col1"><a href="http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/ui/catalog/package-summary.html" format="html" scope="external">com.adobe.primetime.reference.ui.catalog</a> </td> 
    <td colname="col2">Contains UI code for the catalog. </td> 
   </tr> 
   <tr> 
    <td colname="col1"><a href="http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/ui/log/package-summary.html" format="html" scope="external">com.adobe.primetime.reference.ui.log</a> </td> 
    <td colname="col2">Contains UI code for the log. </td> 
   </tr> 
   <tr> 
    <td colname="col1"><a href="http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/ui/player/package-summary.html" format="html" scope="external">com.adobe.primetime.reference.ui.player</a> </td> 
    <td colname="col2">Contains UI code for the player. </td> 
   </tr> 
   <tr> 
    <td colname="col1"><a href="http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/ui/settings/package-summary.html" format="html" scope="external">com.adobe.primetime.reference.ui.settings</a> </td> 
    <td colname="col2">Contains UI code for settings. </td> 
   </tr> 
   <tr> 
    <td colname="col1"><a href="http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/utils/package-summary.html" format="html" scope="external">com.adobe.primetime.reference.utils</a> </td> 
    <td colname="col2">Contains general utility classes. </td> 
   </tr> 
   <tr> 
    <td colname="col1"><a href="http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/utils/http/package-summary.html" format="html" scope="external">com.adobe.primetime.reference.utils.http</a> </td> 
    <td colname="col2">Contains HTTP-specific utility classes. </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

The Primetime reference implementation contains the following packages:
