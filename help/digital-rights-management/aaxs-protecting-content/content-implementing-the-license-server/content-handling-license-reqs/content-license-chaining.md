---
seo-title: License chaining
title: License chaining
uuid: dcc12663-ef9e-4c73-b837-66fcec39358b
---

# License chaining{#license-chaining}

If the policy used to generate the license supports license chaining, the server must decide whether to issue a Leaf license, Root license, or both. To determine what type of license chaining a policy supports, use `Policy.getLicenseChainType()`, or call `Policy.getRootLicenseId()` to determine if the policy has a root license. With Adobe Access 2.0 license chaining, the server typically issues a leaf license the first time the user requests a license for a particular machine and a root license thereafter. To determine if the machine already has a leaf license for the specified policy, call `LicenseRequestMessage.clientHasLeafForPolicy()`. 
