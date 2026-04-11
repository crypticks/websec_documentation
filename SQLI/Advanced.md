Sometimes, its not just direct strings from the packet that are given to the query. JSON/XML data can also be processed to give parameters for the query. These can be modified.

```XML
<stockCheck> 
	<productId>123</productId> 
	<storeId>999 &#x53;ELECT * FROM information_schema.tables</storeId>
</stockCheck>
```
This has encoded the S in SELECT to bypass WAFs and protection mechanisms. Any character could thus be encoded.


#### Second Order ( Stored )

The injection remains dormant in the database till some other command runs using that data. This is just entering some data, which gets trusted by some other script since its stored on the database.