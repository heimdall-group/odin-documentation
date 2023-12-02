Description: Removes keys from the provided Object. This is to optimize API fetching. Developers can in their request specify which keys they wish to not include in the response.

  

### Implementation:

Wrap your [[Server Return]] object with removeRequestKeys function and pass the Event as the second parameter. This function will look for a key named remove in request Body. If this key is provided and is an Array the provided keys will be removed if they exist.

```
export default defineEventHandler(async (event): Promise<PagnationReturn> => {
  try {
    ...
    return await removeRequestKeys({
      data: {
        ...
      },
			type: "Pagination" | "Object" | "Standard" | "Array",
      success: true,
    }, event);
  } catch (error: any) {
    throw createError({
      statusCode: 400,
      statusMessage: error,
    });
  }
});
```

### Different Types:

|   |   |
|---|---|
|Type|Description|
|Pagination|A [[PaginationReturn]] Object. If the Result Array store objects the keys will be removed from these. If not they will be ignored.|
|Object|A normal Object. Keys will be removed from this Object|
|Standard|Any other type that isnt a normal Object or [[PaginationReturn]]. Keys will not be removed from this type. Can be applied to all returns if removal of keys arent to be supported.|
|Array|An Array of Object types|

  

Parameters:

|   |   |   |
|---|---|---|
|Name|Type|Description|
|ReturnObject|[[Return]]|The [[Return]] object that Keys are supposed to be removed from|
|Event|Event|The event that is passed to the function from defineEventHandler|

Returns:

The provided [[Return]] Object but with the data keys specified in Event Body.remove deleted.