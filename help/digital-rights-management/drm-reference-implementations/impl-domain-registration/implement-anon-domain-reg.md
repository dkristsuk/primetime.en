---
seo-title: Implement anonymous domain registration
title: Implement anonymous domain registration
uuid: 330d32fd-8c23-40f9-949b-635e5a9acc86
---

# Implement anonymous domain registration{#implement-anonymous-domain-registration}

1. Create a DRM policy that specifies that domain registration is required.
1. Specify the domain server URL as:

   ```
   https://[host:port]/flashaccess/domainserver/domainname/
   ```

1. Make anonymous authentication mandatory.

   In your [!DNL .properties] file, set: 

   ```
   policy.domain.anonymous=true 
   ```
