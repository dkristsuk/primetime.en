---
description: To enable running and debugging the project directly from the web server you need to change the output folder for each module in IntelliJ to output to your web server's webroot.
seo-description: To enable running and debugging the project directly from the web server you need to change the output folder for each module in IntelliJ to output to your web server's webroot.
seo-title: Enable running and debugging your project
title: Enable running and debugging your project
---

# Enable running and debugging your project

>1. Create a directory in your web server's webroot called `filepath pmp-desktop`.
>   
>1. In IntelliJ, select `uicontrol File` &gt; `uicontrol Project Structure` from the top menu.
>   
>1. Under Project Settings, select `uicontrol Modules`.
>   
>1. Expand the build configurations for each module.
>   
>1. Select the module's build configuration.
>   
>1. Select the `uicontrol General` tab.
>   
>1. Edit the Output folder to point to your web server's webroot `filepath pmp-desktop` directory.
>   Make sure to append the current module's name to the end of the path. For example,`filepath /path/to/webserver/root/pmp-desktop/ReferencePlayer`.
>   >[!NOTE]
>   >
>   >You need to have write permission to the output folder or your project will not build.
>   
>   
>1. Repeat steps 5. through 7. for the remaining modules.
>   
>1. Click `uicontrol OK` at the bottom of the window to accept the changes.
>   
>1. From the top menu, select `uicontrol Build` &gt; `uicontrol Rebuild Project`.
>   
>   