---
seo-title: Install Tomcat
title: Install Tomcat
uuid: f7663eda-ad18-4a6e-bb9f-01c74721b047
---

# Install Tomcat {#install-tomcat}

 You must install Tomcat on both of your servers. 
1. Install Tomcat from the [!DNL \Third Party\Tomcat\6.0.18\] directory on the installation DVD.

   >[!NOTE]
   >
   >Ensure Tomcat is installed in a location where there are no spaces in the path. You can enter `C:\Program Files\Tomcat`, but not `C:\Tomcat\`.

1. To start Tomcat, enter `TomcatInstallDir>\bin\catalina.bat run`.
1. To verify installation, go to the Tomcat landing page by entering `https://<Hostname>:8080/`.
1. Create a `crossdomain.xml` file and place the file in the `<TomcatInstallDir>\webapps\ROOT\` directory.

   You can also copy a file from the `https://drmtest2.adobe.com/crossdomain.xml` directory.
