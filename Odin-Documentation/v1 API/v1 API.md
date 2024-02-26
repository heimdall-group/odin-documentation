---
Created by: felix rydberg
Created time: 2023-11-03T20:30
Last edited by: felix rydberg
Last edited time: 2023-11-21T23:02
---
### General Concepts:

- When having to fetch user permissions make use of the [[getPermissionsObject]] utility function to get an Object with information about the provided User / Access token.
- Before inserting information into MongoDB encrypt the Object with the [[prepareDocument]] utility function.
- After fetching information from MongoDB make sure to decrypt the information with [[readDocument]] utility function
- If you wish to exclude keys from the response make use of the [[removeRequestKeys]] utility function.  
    This function is available on all POST, PUT and DELETE routes.

  

### Utility Functions:

|Name|Description|
|---|---|
|[[createCustomToken]]|Mints custom token for Firebase-auth|
|[[getPermissionsObject]]|Provides permissions and information about a request token (Access key or token)|
|[[prepareDocument]]|Encrypts provided Object keys|
|[[readDocument]]|Decrypts provided Object keys|
|[[writeEncryption]]|Encrypts provided String|
|[[readEncryption]]|Decrypts provided String|
|[[removeRequestKeys]]|Removes keys from Object|
| [getEventsPipeline](getEventsPipeline.md) | Returns a pipeline for getting events |

  

### Adding new API routes:

- Before adding new routes please take some time to learn the [General Concepts](#General%20Concepts) of Odin API structure and [Nuxt Server structure](https://nuxt.com/docs/guide/directory-structure/server).
- Utility functions are provided and imported automatically. You can read more about them [Utility Functions](#Utility%20Functions).
- Each new added route needs to follow the basic feature set shown in [Required features on specific routes](#Required%20features%20on%20specific%20routes)
- When checking if a user has permissions to use a specific endpoint use getPermissionsObject. This will return an object with different keys, one of them being super_admin. If the super-admin key is true this should override any other permissions statuses. An example of an if condition to deny access: 
```
const { data, success, error } = await getPermissionsObject(token);
const { permissions, member, super_admin } = data;
if (!permissions.upload.write && !super_admin) {
	throw 'Permission denied'
}
```


  

### Required features on specific routes:

|Name|Methods|
|---|---|
|[[removeRequestKeys]]|POST, PUT, DELETE|
|||

  

### Endpoints:

All endpoints are prefixed with api/v1

|Url|Page|Description|
|---|---|---|
|v1/authenticate|[[authenticate]]|A collection of endpoints to Authenticate different requests.|
|v1/news|[[news]]|A collection of endpoints for publishing and getting News.|