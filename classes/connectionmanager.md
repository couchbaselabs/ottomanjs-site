# Class: ConnectionManager

Creates a connection instance.
Provide functions to work with cluster, bucket and collection on the current connection.
Supports multiple instances.

**`example`** 
```javascript
 import { connect } from "ottoman";
 const connection: ConnectionManager
                       = connect("couchbase://localhost/travel-sample@admin:password");
 ```

## Hierarchy

* **ConnectionManager**

## Constructors

###  constructor

\+ **new ConnectionManager**(`cluster`: any, `bucketName`: string, `couchbase`: any): *[ConnectionManager](connectionmanager.md)*

**Parameters:**

Name | Type |
------ | ------ |
`cluster` | any |
`bucketName` | string |
`couchbase` | any |

**Returns:** *[ConnectionManager](connectionmanager.md)*

## Properties

###  bucket

• **bucket**: *any*

Bucket represents a storage grouping of data within a Couchbase Server cluster.

___

###  bucketName

• **bucketName**: *string*

Contains the name of the current bucket.

___

###  cluster

• **cluster**: *any*

Cluster represents an entire Couchbase Server cluster.

___

###  collectionManager

• **collectionManager**: *any*

CollectionManager allows the management of collections within a Bucket.

___

###  couchbase

• **couchbase**: *any*

Stores a reference to couchbase instance.

___

###  models

• **models**: *object*

Dictionary for all models registered on this connection.

#### Type declaration:

___

###  queryIndexManager

• **queryIndexManager**: *any*

QueryIndexManager provides an interface for managing the query indexes on the cluster.

___

###  viewIndexManager

• **viewIndexManager**: *any*

ViewIndexManager is an interface which enables the management of view indexes on the cluster.

## Methods

###  close

▸ **close**(): *void*

Closes the current connection

**`example`** 
```javascript
connection.close().then(() => console.log('connection closed'));
```

**Returns:** *void*

___

###  getCollection

▸ **getCollection**(`collectionName`: string, `scopeName`: string): *any*

Return a collection from the given collectionName in this bucket
Or default collection if collectionName is missing

**Parameters:**

Name | Type | Default |
------ | ------ | ------ |
`collectionName` | string | DEFAULT_COLLECTION |
`scopeName` | string | DEFAULT_SCOPE |

**Returns:** *any*

___

###  getModel

▸ **getModel**(`name`: string): *[ModelTypes](../globals.md#modeltypes)*

Returns a Model constructor from the given name

**`example`** 
```javascript
const User = connection.getModel('User');
```

**Parameters:**

Name | Type |
------ | ------ |
`name` | string |

**Returns:** *[ModelTypes](../globals.md#modeltypes)*

___

###  model

▸ **model**(`name`: string, `schema`: [Schema](schema.md) | Record‹string, unknown›, `options?`: any): *object & object*

Creates a Model on this connection.

**`example`** 
```javascript
const User = connection.model('User', { name: String }, {collectionName: 'users'});
```

**Parameters:**

Name | Type |
------ | ------ |
`name` | string |
`schema` | [Schema](schema.md) &#124; Record‹string, unknown› |
`options?` | any |

**Returns:** *object & object*

___

###  query

▸ **query**(`query`: string): *Promise‹any›*

Executes N1QL Queries.

Ottoman provides a powerful [Query Builder](/guides/query-builder) system to create valid N1QL queries in a easier way.
See the example below:

**`example`** 
```javascript
const expr_where = {$or: [{ address: { $like: '%57-59%' } }, { free_breakfast: true }]};
const query = new Query({}, 'travel-sample');
const n1qlQuery = query.select([{$field: 'address'}]).where(expr_where).build()

connection.query(n1qlQuery).then(result => console.log(result))
```
The above example will run this query:
> `SELECT address FROM travel-sample WHERE (address LIKE '%57-59%' OR free_breakfast = true)`

**Parameters:**

Name | Type |
------ | ------ |
`query` | string |

**Returns:** *Promise‹any›*

___

###  start

▸ **start**(`__namedParameters`: object): *Promise‹void›*

Ensure that Ottoman start correcty

**Parameters:**

▪`Default value`  **__namedParameters**: *object*= {}

Name | Type | Default | Description |
------ | ------ | ------ | ------ |
`ensureIndexes` | boolean | true | is a flag that defines when Ottoman must ensure that all indexes are created on the server |
`useCollections` | boolean | false | is a flag to create scopes/collections.  |

**Returns:** *Promise‹void›*
