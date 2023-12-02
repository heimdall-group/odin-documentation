Description: Creates a news post. The article will either be marked as Public or Internal (If permissions allow for it).

  

  

Parameters:

|Name|Type|Description|
|---|---|---|
|title|String|Title of the news article|
|body|String|Body of the news article. Supports [[v1 Markdown]]|
|internal|Boolean|If the article is internal|
|public|Boolean|If the article is public|

Returns:

A [[Server Return]] Object with the following data set to true if successful.