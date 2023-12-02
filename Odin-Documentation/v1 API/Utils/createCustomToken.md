  

Description:

Creates a custom Firebase-auth token corresponding to that Discord users Firebase auth profile. If its a new user a new profile will be created by Firebase.

  

Parameters:

|Name|Type|Description|
|---|---|---|
|auth|Firebase-admin Auth Object|Firebase-admin Auth instance|
|uid|String|Discord user uid|
|expires_in|Number|When the discord authentication expires|

Returns:

A [[Return]] Object with the following data.

|Name|Type|Description|
|---|---|---|
|customToken|String|A custom Firebase auth token|