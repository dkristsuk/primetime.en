---
seo-title: Custom metadata
title: Custom metadata
uuid: 9433fd74-730d-4306-8ff3-a6857745a039
---

# Custom metadata {#custom-metadata}

**Specify custom key/value to add to content metadata that can be interpreted by the server application.**

The Adobe Access content metadata format allows for inclusion of custom key/value pairs at packaging time to be processed by the license server during license issuance. This metadata is separate from the policy and can be unique for each piece of content.

Example use case: During a Beta phase, you include the custom property "Release:BETA" at packaging time. License servers can vend licenses to this content during the Beta period, but after the Beta period expires, the license servers disallow access to the content. 
