Description:

A server specific [[Return]] type. Contains keys to improve RnD when trying to prevent errors in the future.

  

|Name|Type|Description|
|---|---|---|
|data (Optional)|Any|Request specific. The data returned from the function / endpoint|
|message (Optional)|String|Provided error message|
|stack (Optional)|String|Error stack|
|statusCode (Optional)|Number|Status code of the Error|
|statusMessage (Optional)|String|Provided error message|
|success (Optional)|Boolean|Indicates if request was successfull or not|
|type|“Pagnation”  <br>”Object”  <br>”Standard”|Indicates type to [[removeRequestKeys]]. More information about types can be found [[removeRequestKeys]].|
|url (Optional)|String|The request url|