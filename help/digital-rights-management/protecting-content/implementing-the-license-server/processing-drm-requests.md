---
seo-title: Process Adobe Primetime DRM requests
title: Process Adobe Primetime DRM requests
uuid: ee10504d-84f0-472a-b58a-2a87fdeedfc1
---

# Process Adobe Primetime DRM requests {#process-adobe-primetime-drm-requests}

The general approach to managing requests is to create a handler, parse the request, set the response data or error code, and close the handler.

The base class used to handle single request/response interaction is `com.adobe.flashaccess.sdk.protocol.MessageHandlerBase`. An instance of the `HandlerConfiguration` class is used to initialize the handler. `HandlerConfiguration` stores server configuration information, including transport credentials, timestamp tolerance, policy update lists, and revocation lists.The handler reads the request data and parses the request into an instance of `RequestMessageBase`. The caller can examine the information in the request and decide whether to return an error or a successful response (subclasses of `RequestMessageBase` provide a method for setting response data).

If the request is successful, set the response data; otherwise invoke `RequestMessageBase.setErrorData()` on failure. Always end the implementation by invoking the `close()` method (it is recommended that `close()` be called in the `finally` block of a `try` statement). See the `MessageHandlerBase` API reference documentation for an example of how to invoke the handler.

>[!NOTE] {class="- topic/note "}
>
>HTTP status code 200 (OK) should be sent in response to all requests processed by the handler. If the handler could not be created due to a server error, the server may respond with another status code, such as 500 (Internal Server Error).

The client uses the License Server URL specified at packaging time as the base URL for all requests sent to the license server. For example, if the server URL is specified as <[!DNL ht<span></span>tps://licenseserver.com/path]>, the client then sends requests to <[!DNL ht<span></span>tps://licenseserver.com/path/flashaccess/...]> See the following sections for details on the specific path used for each type of request. When implementing your license server, be sure the server responds to the paths required for each type of request.

A license request can contain an authentication token. If username/password authentication was used, the request may contain an `AuthenticationToken` generated by the `AuthenticationHandler`, and the SDK will ensure the token is valid before issuing a license.

## Use machine identifiers {#use-machine-identifiers}

All Adobe Primetime DRM requests (with the exception of requests supporting FMRMS compatibility) include information about the machine token that has been issued to the client during individualization. The machine token includes a Machine Id, which is an identifier that has ben assigned during individualization. You can use this identifier to count the number of machines from which a user has requested a license or joined a domain.

You can use an identifier as follows:

* The `getUniqueId()` method returns a string that has been assigned to a device during individualization. You can store the strings in a database and search by identifier. However, this identifier changes if the user reformats the hard drive and individualizes again. This identifier also has a different value between Adobe AIR and Adobe Flash Player in different browsers on the same machine. 
* If you want to more accurately count machines, you can use `getBytes()` to store the whole identifier. To determine if the machine has been seen before, get all the identifiers for a user name and call `matches()` to check if any match. Because the `matches()` method must be used to compare the values returned by `MachineId.getBytes`, this option is only practical when there are a small number of values to compare; for example, the machines associated with a particular user.

## User authentication {#user-authentication}

An Adobe Primetime DRM request can contain an authentication token.

If username/password authentication was used, the request may include an `AuthenticationToken` generated by the `AuthenticationHandler`. If you want to access and verify the token, you need to use `RequestMessageBase.getAuthenticationToken()`. To initiate a username/password request on the client, use the `DRMManager.authenticate()` ActionScript or iOS API.

If the client and server use a custom authentication mechanism, the client obtains an authentication token through some other channel and sets the custom authentication token using the `DRMManager.setAuthenticationToken` ActionScript 3.0 API. Use `RequestMessageBase.getRawAuthenticationToken()` to get the custom authentication token. The server implementation determines whether the custom authentication token is valid.

## Replay protection {#replay-protection}

For replay protection, you may want to check whether the message identifier has been seen recently by calling `RequestMessageBase.getMessageId()`. If so, an attacker may be trying to replay the request, which should be denied. To detect replay attempts, the server can store a list of recently seen message ids and check each incoming request against the cached list. To limit the amount of time the message identifiers need to be stored, call `HandlerConfiguration.setTimestampTolerance()`. If this property is set, the SDK then denies any request that carries a timestamp for more than the specified number of seconds off the server time.

## Rollback detection {#rollback-detection}

For rollback detection, some usage rules require the client to maintain state information for enforcement of the rights. For example, to enforce the playback window usage rule, the client stores the date and time when the user first began viewing the content. This event triggers the start of the playback window. To securely enforce the playback window, the server needs to ensure that the user is not backing up and restoring the client state to remove the playback window start time stored on the client. The server does this by tracking the value of the client's rollback counter.

For each request, the server gets the value of the counter by calling `RequestMessageBase.getClientState()` to obtain the `ClientState` object, then calling `ClientState.getCounter()` to obtain the current value of the client state counter. The server should store this value for each client (use `MachineId.getUniqueId()` to identify the client associated with the rollback counter value), and then call `ClientState.incrementCounter()` to increase the counter value by one. If the server detects that the counter value is less than the last value seen by the server, the client state may have been rolled back.

See the `ClientState` API reference documentation for more information on client state tamper detection.

## Global server configuration data{#global-server-configuration-data}

In addition to configuration used by the license server, `HandlerConfiguration` stores configuration information that can be sent to the client to control how licenses are enforced. This is done by creating a `ServerConfigData` class and calling `HandlerConfiguration.setServerConfigData()`. These settings apply only to licenses issued by this license server.

The clock windback tolerance is one property that can be set by the license server to control how the client enforces licenses. By default, users may set their machine clock back 4 hours without invalidating licenses. If a license server operator wishes to use a different setting, the new value can be set in the `ServerConfigData` class. When you change the value of any of these settings, be sure to increment the version number by calling `setVersion()`. The new values are only sent to the client if the version on the client is older than the current `ServerConfigData` version. 

## Crossdomain DRM policy file {#crossdomain-drm-policy-file}

If the license server is hosted on a different domain than the video playback SWF, then a cross-domain DRM policy file ( [!DNL crossdomain.xml]) is needed to enable the SWF to request licenses from a license server. A cross-domain DRM policy file is represented by an XML file that enables the server to indicate that its data and documents are available to SWF files served from other domains. Any SWF file served from a domain specified in the license server's cross-domain DRM policy file is permitted to access data or assets from that license server.

Adobe recommends that developers follow best practices when deploying the cross-domain policy file by only allowing trusted domains to access the license server and limiting the access to the license sub-directory on the web server.

For more information on cross-domain DRM policy files, see the following locations:

* Web site controls (DRM policy files)
* Cross-domain DRM policy file specification: [https://www.adobe.com/devnet/articles/crossdomain_policy_file_spec.html](https://www.adobe.com/devnet/articles/crossdomain_policy_file_spec.html)