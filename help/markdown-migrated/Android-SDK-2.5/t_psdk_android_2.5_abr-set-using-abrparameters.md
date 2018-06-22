---
description: You can set ABR control values only with ABRControlParameters, but you can construct a new one at any time.
seo-description: You can set ABR control values only with ABRControlParameters, but you can construct a new one at any time.
seo-title: Configure adaptive bit rates using ABRControlParameters
title: Configure adaptive bit rates using ABRControlParameters
---

# Configure adaptive bit rates using ABRControlParameters

The following conditions apply to `codeph  ABRControlParameters`:
* At construction time, you must provide values for all parameters.
* After the construction, you cannot change individual values.
* If the parameters that you specify are outside of the allowed range, an `codeph  ArgumentError` is thrown.

>1. Determine your initial, minimum, and maximum bit rates.
>   
>1. Determine the ABR policy:
>* `codeph  ABR_CONSERVATIVE`
>* `codeph  ABR_MODERATE`
>* `codeph  ABR_AGGRESSIVE`
>   
>   
>1. Set the ABR parameter values in the `codeph  ABRControlParameters` constructor and assign the values to the Media Player.
>   ```
>   public ABRControlParameters(int initialBitRate, 
>    int minBitRate, 
>    int maxBitRate, 
>    ABRControlParameters.ABRPolicy abrPolicy, 
>    int minTrickPlayBitRate, 
>    int maxTrickPlayBitRate, 
>    int maxTrickPlayBandwidthUsage, 
>    int maxPlayoutRate);
>   ```
>   
>   
>   