---
seo-title: Password Scrambler
title: Password Scrambler
uuid: e488babc-cd50-41b9-acb8-490e8e42e8bc
---

# Password Scrambler {#password-scrambler}

The Password Scrambler utility encrypts a password so that it can be used in the Adobe Access Server for Protected Streaming configuration files. To run the scrambler, run the command:

```
Scrambler.bat password 
```

or the command:

```
java -jar libs/flashaccess-scrambler.jar password  
```

The utility outputs the following message:

```
Encrypted password: scrambled-password 
```

All passwords specified in flashaccess-global.xml and flashaccess-tenant.xml must be encrypted.

>[!NOTE]
>
>The Password Scrambler utility in the Adobe Access Server for Protected Streaming is not interchangeable with the scrambler provided with the Reference Implementation License Server.

