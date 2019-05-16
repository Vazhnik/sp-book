## General
https://aws.amazon.com/ru/blogs/database/choosing-the-right-dynamodb-partition-key/

DynamoDB supports two types of primary keys:
- Partition key: обычный ключ
- Partition key and sort key: == composite primary key - Состоит из двух аттрибутов. The first attribute is the partition key, and the second attribute is the sort key. Following is an example.

Динамо распределяет контент по партишнам, каждый около 10 гб

Одна таблица содержит один и более партишнов.


If the table has a composite primary key (partition key and sort key), DynamoDB calculates the hash value of the partition key in the same way as described in Data Distribution: Partition Key—but it stores all of the items with the same partition key value physically close together, ordered by sort key value.


https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBMapper.Methods.html

## Reads Consistency
- Eventually Consistent Reads
- Strongly Consistent Reads


HashKey - больше как реальный primary, а rangeKey - больше как вспомогательный
Нельзя искать по rangeKey без hashKey,
НО!
можно создать индекс на табилце, где rangeKey таблицы будет hashKey в новом индексе. тогда можно будет сёрчить сам индекс по его hashKey.
