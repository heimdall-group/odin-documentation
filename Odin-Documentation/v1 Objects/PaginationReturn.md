Description:

A server specific [[Server Return]]. Includes keys for pagination to cache the amount of results that has already been delivered and collection size.

This is an extension of [[Server Return]] so the keys provided here are only the changes made from [[Server Return]].

  

|Name|Type|Description|
|---|---|---|
|data.limit|number|Max amount of items per request|
|data.skip|number|Amount of items delivered|
|data.collection_size|number|Size of collection|
|data.result|Array|Results from query|