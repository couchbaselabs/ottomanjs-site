# Class: Ottoman

## Hierarchy

* **Ottoman**

## Constructors

###  constructor

\+ **new Ottoman**(`config`: [OttomanConfig](../interfaces/ottomanconfig.md)): *[Ottoman](ottoman.md)*

**Parameters:**

Name | Type | Default |
------ | ------ | ------ |
`config` | [OttomanConfig](../interfaces/ottomanconfig.md) | {} |

**Returns:** *[Ottoman](ottoman.md)*

## Properties

###  bucket

• **bucket**: *any*

Bucket represents a storage grouping of data within a Couchbase Server cluster.

___

###  bucketName

• **bucketName**: *string* = ""

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

###  config

• **config**: *[OttomanConfig](../interfaces/ottomanconfig.md)*

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

###  connect

▸ **connect**(`connectOptions`: [ConnectOptions](../interfaces/connectoptions.md) | string): *this*

Connect to Couchbase server

**`example`** 
```javascript
 import { connect } from "ottoman";
 const connection = connect("couchbase://localhost/travel-sample@admin:password");
```

**Parameters:**

Name | Type |
------ | ------ |
`connectOptions` | [ConnectOptions](../interfaces/connectoptions.md) &#124; string |

**Returns:** *this*

___

###  ensureCollections

▸ **ensureCollections**(): *Promise‹void›*

`ensureCollections` will attempt to create scopes and collection to map your models into Couchbase Server.

**Returns:** *Promise‹void›*

___

###  ensureIndexes

▸ **ensureIndexes**(): *Promise‹void›*

`ensureIndexes` will attempt to create indexes defined in your schemas

**Returns:** *Promise‹void›*

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

▸ **model**(`name`: string, `schema`: [Schema](schema.md) | Record‹string, unknown›, `options`: [ModelOptions](../interfaces/modeloptions.md)): *[ModelTypes](../globals.md#modeltypes)*

Creates a Model on this connection.

**`example`** 
```javascript
const User = connection.model('User', { name: String }, {collectionName: 'users'});
```

**Parameters:**

Name | Type | Default |
------ | ------ | ------ |
`name` | string | - |
`schema` | [Schema](schema.md) &#124; Record‹string, unknown› | - |
`options` | [ModelOptions](../interfaces/modeloptions.md) | {} |

**Returns:** *[ModelTypes](../globals.md#modeltypes)*

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

▸ **start**(): *Promise‹void›*

`start` method is just a shortcut to run `ensureCollections` and `ensureIndexes`.
 Notice: It's not required to execute the `start` method to Ottoman work.

**Returns:** *Promise‹void›*
