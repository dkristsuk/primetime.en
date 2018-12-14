---
description: null
seo-description: null
seo-title: Prepare passwords for the Server properties files
title: Prepare passwords for the Server properties files
uuid: 90de6c11-9877-4c26-a32a-5927ed5470a4
index: y
internal: n
snippet: y
---

# Prepare passwords for the Server properties files{#prepare-passwords-for-the-server-properties-files}

The reference implementation provides `ScrambleUtil.class`, a class that ensures the security of your credential's password. 

1. Use this tool to encrypt the password before you include it in the [!DNL flashaccess-refimpl.properties] file.

   To run the tool, you can use either an Ant script or Java.
>The utility generates the encrypted password, which you must copy to the [!DNL flashaccess-refimpl.properties] file. 
>
>>[!NOTE] {class="- topic/note "}
>>
>>Passwords that have been encoded with the `ScrambleUtil.class` that has been provided with the reference implementation do not work with the Primetime DRM Server for Protected Streaming. 
>