---
seo-title: Troubleshooting
title: Troubleshooting
uuid: db76d6a4-c285-4d86-95a1-4f1a85ed3743
---

# Troubleshooting {#troubleshooting}

Listed below are common problems and solutions for deployment:

* If you see the following error:

  ```
      "Error decoding the password for HandlerConfiguration.ServerTransportCredential.password  
      javax.crypto.IllegalBlockSizeException: Input length must be multiple of 8 when decrypting with padded cipher"
  ```

  Make sure the password is encrypted using the provided `ScrambleUtil` class. 

* If you see the following error:

  ```
      "Unable to load credential from file.pfx -- possibly wrong password."
  ```

  Make sure you specified the correct encrypted password for the PFX file. 

* If you see the following error:

  ```
      "javax.crypto.BadPaddingException: Given final block not properly padded"
  ```

  Make sure you used the password scrambler class provided with the Reference Implementation (this scrambler utility is different from the one provided with the Adobe® Access™ Server for Protected Streaming).

