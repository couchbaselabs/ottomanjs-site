# Ottoman

## Type aliases

###  AggType

Ƭ **AggType**: *"$arrayAgg" | "$avg" | "$mean" | "$count" | "$countn" | "$max" | "$median" | "$min" | "$stddev" | "$stddevPop" | "$stddevSamp" | "$sum" | "$variance" | "$variancePop" | "$varianceSamp" | "$varPop" | "$varSamp"*

List of aggregation functions.

___

###  AutoFunction

Ƭ **AutoFunction**: *function*

#### Type declaration:

▸ (): *unknown*

___

###  CollectionInWithinOperator

Ƭ **CollectionInWithinOperator**: *"$in" | "$within"*

Collection IN and WITHIN Operators.

___

###  CollectionInWithinOperatorType

Ƭ **CollectionInWithinOperatorType**: *object*

Structure of the collection in within operator

**`example`** 
```
{$in:{search_expr: 'search', target_expr: 'address', $not: true}}
```

#### Type declaration:

___

###  CollectionSatisfiesOperator

Ƭ **CollectionSatisfiesOperator**: *"$satisfies"*

List of Collection IN and WITHIN Operators.

___

###  CollectionSelectOperator

Ƭ **CollectionSelectOperator**: *"$any" | "$every"*

Collection Select Operator.

___

###  CollectionSelectOperatorType

Ƭ **CollectionSelectOperatorType**: *object*

Structure of the collection in within operator

**`example`** 
```
{$any: {$expr: [{$in:{search_expr: 'search', target_expr: 'address', $not: true} }], $satisfied:{address: '10'}}}
```

#### Type declaration:

___

###  ComparisonEmptyOperatorType

Ƭ **ComparisonEmptyOperatorType**: *"$isNull" | "$isNotNull" | "$isMissing" | "$isNotMissing" | "$isValued" | "$isNotValued"*

List of Boolean comparison operators.

___

###  ComparisonMultipleOperatorType

Ƭ **ComparisonMultipleOperatorType**: *"$btw" | "$notBtw"*

List of Range comparison operators.

___

###  ComparisonSingleOperatorType

Ƭ **ComparisonSingleOperatorType**: *"$eq" | "$neq" | "$gt" | "$gte" | "$lt" | "$lte"*

List of Numeric comparison operators.

___

###  ComparisonSingleStringOperatorType

Ƭ **ComparisonSingleStringOperatorType**: *"$like" | "$notLike"*

List of String comparison operators.

___

###  ComparisonWhereExpr

Ƭ **ComparisonWhereExpr**: *object*

Structure of the comparison operators.

**`example`** 
```
{operator: value} -> e.g { $like: '%ottoman%'}
```

#### Type declaration:

___

###  CountOptions

Ƭ **CountOptions**: *object*

#### Type declaration:

* **limit**? : *undefined | number*

* **skip**? : *undefined | number*

* **sort**? : *Record‹string, [SortType](globals.md#sorttype)›*

___

###  CustomValidations

Ƭ **CustomValidations**: *object*

#### Type declaration:

* \[ **key**: *string*\]: [ValidatorFunction](globals.md#validatorfunction)

___

###  DateFunction

Ƭ **DateFunction**: *function*

#### Type declaration:

▸ (): *Date | [DateOption](interfaces/dateoption.md)*

___

###  FactoryFunction

Ƭ **FactoryFunction**: *function*

#### Type declaration:

▸ (`name`: any, `options`: any): *[IOttomanType](classes/iottomantype.md)*

**Parameters:**

Name | Type |
------ | ------ |
`name` | any |
`options` | any |

___

###  FieldMap

Ƭ **FieldMap**: *object*

#### Type declaration:

* \[ **key**: *string*\]: [IOttomanType](classes/iottomantype.md)

___

###  FieldWhereExpr

Ƭ **FieldWhereExpr**: *Record‹string, string | number | boolean | [ComparisonWhereExpr](globals.md#comparisonwhereexpr)› | [LogicalWhereExpr](globals.md#logicalwhereexpr)*

Structure of WHERE field expression

**`example`** 
```
{field: {operator: value}} -> e.g { address: {$like: '%ottoman%'}} | {$or: [{ address: {$like: '%ottoman%'}}]}
```

___

###  FunctionsString

Ƭ **FunctionsString**: *function*

#### Type declaration:

▸ (): *string[]*

___

###  Hook

Ƭ **Hook**: *object*

#### Type declaration:

___

###  HookHandler

Ƭ **HookHandler**: *function*

#### Type declaration:

▸ (`IDocument`: any): *void*

**Parameters:**

Name | Type |
------ | ------ |
`IDocument` | any |

___

###  HookTypes

Ƭ **HookTypes**: *[HOOKS](enums/hooks.md) | "validate" | "save" | "update" | "remove"*

___

###  ISelectAggType

Ƭ **ISelectAggType**: *object*

SELECT aggregation expression

**`example`** 
```
 {$count: {$field: {name: 'address'}, as: 'addr'}} | {$count: {$field: 'address'}}
```

#### Type declaration:

___

###  ISelectResultExprType

Ƭ **ISelectResultExprType**: *object*

SELECT result expression

**`example`** 
```
 {$raw: {$field: {name: 'address'}, as: 'addr'}}
```

#### Type declaration:

___

###  ISelectReturnResultType

Ƭ **ISelectReturnResultType**: *object*

SELECT result expression

**`example`** 
```
 {$all: {$field: {name: 'address'}, as: 'addr'}}
```

#### Type declaration:

___

###  ISelectType

Ƭ **ISelectType**: *[ISelectReturnResultType](globals.md#iselectreturnresulttype) | [ISelectResultExprType](globals.md#iselectresultexprtype) | [ISelectAggType](globals.md#iselectaggtype) | [ISelectFieldType](interfaces/iselectfieldtype.md)*

SELECT expression

**`example`** 
```
 {$all: {$field: {name: 'address'}, as: 'addr'}, $field: 'type', $field: {name: 'count'}}
```

___

###  IndexType

Ƭ **IndexType**: *"refdoc" | "n1ql" | "view"*

Types of supported index statements

___

###  LogicalOperatorType

Ƭ **LogicalOperatorType**: *"$and" | "$or" | "$not"*

List of Logical operators.

___

###  LogicalWhereExpr

Ƭ **LogicalWhereExpr**: *object | object | [CollectionSelectOperatorType](globals.md#collectionselectoperatortype) | [CollectionInWithinOperatorType](globals.md#collectioninwithinoperatortype)*

Structure of Logical WHERE expression

**`example`** 
```
{field: {operator: value}} -> e.g {$or: [{ address: {$like: '%ottoman%'}}]}
```

___

###  ModelTypes

Ƭ **ModelTypes**: *[WhateverTypes](globals.md#whatevertypes) & object*

___

###  NumberFunction

Ƭ **NumberFunction**: *function*

#### Type declaration:

▸ (): *number | [MinmaxOption](interfaces/minmaxoption.md)*

___

###  ParseResult

Ƭ **ParseResult**: *object*

#### Type declaration:

___

###  PluginConstructor

Ƭ **PluginConstructor**: *function*

#### Type declaration:

▸ (`Schema`: any): *void*

**Parameters:**

Name | Type |
------ | ------ |
`Schema` | any |

___

###  PluginFunctions

Ƭ **PluginFunctions**: *function*

#### Type declaration:

▸ (): *void*

___

###  RequiredFunction

Ƭ **RequiredFunction**: *function*

#### Type declaration:

▸ (): *boolean | [RequiredOption](interfaces/requiredoption.md)*

___

###  ResultExprType

Ƭ **ResultExprType**: *"$raw" | "$element" | "$value"*

Result expressions RAW | ELEMENT | VALUE

___

###  ReturnResultType

Ƭ **ReturnResultType**: *"$all" | "$distinct"*

Result expressions ALL | DISTINCT

___

###  SchemaDef

Ƭ **SchemaDef**: *Record‹string, any›*

___

###  SchemaIndex

Ƭ **SchemaIndex**: *Record‹string, object›*

___

###  SchemaQuery

Ƭ **SchemaQuery**: *Record‹string, object›*

___

###  SortType

Ƭ **SortType**: *"ASC" | "DESC"*

___

###  SupportType

Ƭ **SupportType**: *object*

#### Type declaration:

* \[ **key**: *string*\]: [FactoryFunction](globals.md#factoryfunction)

___

###  ValidatorFunction

Ƭ **ValidatorFunction**: *function*

Should throw all errors detected

#### Type declaration:

▸ (`value`: unknown): *void*

**Parameters:**

Name | Type |
------ | ------ |
`value` | unknown |

___

###  WhateverTypes

Ƭ **WhateverTypes**: *object*

#### Type declaration:

* \[ **key**: *string*\]: any

## Variables

### `Let` COLLECTION_KEY

• **COLLECTION_KEY**: *string* = "_type"

Default value for metadata key, to keep collection tracking
eg. This model new Model('User', schema, options), will generate documents -> document._type = 'User'

___

### `Const` DEFAULT_COLLECTION

• **DEFAULT_COLLECTION**: *"_default"* = "_default"

Default collection name

___

### `Const` DEFAULT_ID_KEY

• **DEFAULT_ID_KEY**: *"id"* = "id"

Key to add document metadata identifier
This key will store the value of the key,
key -> document, document.id === key

___

### `Const` DEFAULT_MAX_EXPIRY

• **DEFAULT_MAX_EXPIRY**: *"300000"* = "300000"

___

### `Let` DEFAULT_POPULATE_MAX_DEEP

• **DEFAULT_POPULATE_MAX_DEEP**: *number* = 1

___

### `Let` DEFAULT_SCOPE

• **DEFAULT_SCOPE**: *string* = "_default"

Default scope name

___

### `Let` DISABLE_SCOPES

• **DISABLE_SCOPES**: *boolean* = false

___

### `Let` SCOPE_KEY

• **SCOPE_KEY**: *string* = "_scope"

Default value to metadata key, to keep scope tracking
eg. This model new Model('User', schema, {scope: 'app'}), will generate documents -> document._scope = 'app'

___

### `Let` __conn

• **__conn**: *[ConnectionManager](classes/connectionmanager.md)*

Store default connection

___

### `Const` __connections

• **__connections**: *[ConnectionManager](classes/connectionmanager.md)[]* = []

___

### `Const` __indexes

• **__indexes**: *Record‹any, object›*

___

### `Const` __plugins

• **__plugins**: *[PluginFunctions](globals.md#pluginfunctions)[]* = []

Store global plugins.

___

### `Const` __refdocIndexes

• **__refdocIndexes**: *Record‹any, object[]›*

___

### `Const` __viewIndexes

• **__viewIndexes**: *Record‹any, object›*

___

###  closeConnection

• **closeConnection**: *(Anonymous function)*

___

###  connect

• **connect**: *(Anonymous function)*

___

###  getCollection

• **getCollection**: *(Anonymous function)*

___

###  getConnections

• **getConnections**: *(Anonymous function)*

___

###  getDefaultConnection

• **getDefaultConnection**: *(Anonymous function)*

___

###  model

• **model**: *[model](classes/ottoman.md#model)*

___

### `Const` modelMetadataSymbol

• **modelMetadataSymbol**: *unique symbol* = Symbol('modelMetadataSymbol')

___

### `Const` n1qlReservedWords

• **n1qlReservedWords**: *string[]* = [
  'ADVISE',
  'ALL',
  'ALTER',
  'ANALYZE',
  'AND',
  'ANY',
  'ARRAY',
  'AS',
  'ASC',
  'BEGIN',
  'BETWEEN',
  'BINARY',
  'BOOLEAN',
  'BREAK',
  'BUCKET',
  'BUILD',
  'BY',
  'CALL',
  'CASE',
  'CAST',
  'CLUSTER',
  'COLLATE',
  'COLLECTION',
  'COMMIT',
  'CONNECT',
  'CONTINUE',
  'CORRELATED',
  'COVER',
  'CREATE',
  'CURRENT',
  'DATABASE',
  'DATASET',
  'DATASTORE',
  'DECLARE',
  'DECREMENT',
  'DELETE',
  'DERIVED',
  'DESC',
  'DESCRIBE',
  'DISTINCT',
  'DO',
  'DROP',
  'EACH',
  'ELEMENT',
  'ELSE',
  'END',
  'EVERY',
  'EXCEPT',
  'EXCLUDE',
  'EXECUTE',
  'EXISTS',
  'EXPLAIN',
  'FALSE',
  'FETCH',
  'FIRST',
  'FLATTEN',
  'FOLLOWING',
  'FOR',
  'FORCE',
  'FROM',
  'FTS',
  'FUNCTION',
  'GOLANG',
  'GRANT',
  'GROUP',
  'GROUPS',
  'GSI',
  'HASH',
  'HAVING',
  'IF',
  'IGNORE',
  'ILIKE',
  'IN',
  'INCLUDE',
  'INCREMENT',
  'INDEX',
  'INFER',
  'INLINE',
  'INNER',
  'INSERT',
  'INTERSECT',
  'INTO',
  'IS',
  'JAVASCRIPT',
  'JOIN',
  'KEY',
  'KEYS',
  'KEYSPACE',
  'KNOWN',
  'LANGUAGE',
  'LAST',
  'LEFT',
  'LET',
  'LETTING',
  'LIKE',
  'LIMIT',
  'LSM',
  'MAP',
  'MAPPING',
  'MATCHED',
  'MATERIALIZED',
  'MERGE',
  'MINUS',
  'MISSING',
  'NAMESPACE',
  'NEST',
  'NL',
  'NO',
  'NOT',
  'NTH_VALUE',
  'NULL',
  'NULLS',
  'NUMBER',
  'OBJECT',
  'OFFSET',
  'ON',
  'OPTION',
  'OPTIONS [1]',
  'OR',
  'ORDER',
  'OTHERS',
  'OUTER',
  'OVER',
  'PARSE',
  'PARTITION',
  'PASSWORD',
  'PATH',
  'POOL',
  'PRECEDING',
  'PREPARE',
  'PRIMARY',
  'PRIVATE',
  'PRIVILEGE',
  'PROBE',
  'PROCEDURE',
  'PUBLIC',
  'RANGE',
  'RAW',
  'REALM',
  'REDUCE',
  'RENAME',
  'RESPECT',
  'RETURN',
  'RETURNING',
  'REVOKE',
  'RIGHT',
  'ROLE',
  'ROLLBACK',
  'ROW',
  'ROWS',
  'SATISFIES',
  'SCHEMA',
  'SELECT',
  'SELF',
  'SEMI',
  'SET',
  'SHOW',
  'SOME',
  'START',
  'STATISTICS',
  'STRING',
  'SYSTEM',
  'THEN',
  'TIES',
  'TO',
  'TRANSACTION',
  'TRIGGER',
  'TRUE',
  'TRUNCATE',
  'UNBOUNDED',
  'UNDER',
  'UNION',
  'UNIQUE',
  'UNKNOWN',
  'UNNEST',
  'UNSET',
  'UPDATE',
  'UPSERT',
  'USE',
  'USER',
  'USING',
  'VALIDATE',
  'VALUE',
  'VALUED',
  'VALUES',
  'VIA',
  'VIEW',
  'WHEN',
  'WHERE',
  'WHILE',
  'WITH',
  'WITHIN',
  'WORK',
  'XOR',
]

___

### `Const` ottoman

• **ottoman**: *[Ottoman](classes/ottoman.md)‹›* = new Ottoman()

___

### `Const` replaceList

• **replaceList**: *string[]* = ['ALL', 'DISTINCT', 'RAW', 'ELEMENT', 'VALUE']

___

###  start

• **start**: *(Anonymous function)*

## Functions

### `Let` KEY_GENERATOR

▸ **KEY_GENERATOR**(`__namedParameters`: object): *string*

**Parameters:**

▪ **__namedParameters**: *object*

Name | Type |
------ | ------ |
`id` | any |
`metadata` | any |

**Returns:** *string*

___

### `Const` _buildModel

▸ **_buildModel**(`metadata`: [ModelMetadata](interfaces/modelmetadata.md)): *_Model*

**Parameters:**

Name | Type |
------ | ------ |
`metadata` | [ModelMetadata](interfaces/modelmetadata.md) |

**Returns:** *_Model*

___

###  addRefKeys

▸ **addRefKeys**(`refKeys`: any, `collection`: any, `key`: any): *AsyncGenerator‹any, void, unknown›*

**Parameters:**

Name | Type |
------ | ------ |
`refKeys` | any |
`collection` | any |
`key` | any |

**Returns:** *AsyncGenerator‹any, void, unknown›*

___

### `Const` addValidators

▸ **addValidators**(`validators`: [CustomValidations](globals.md#customvalidations)): *void*

Register custom validators to Schema validators register.

**`function`** 

**`throws`** Error

**`example`** 
 ```ts
   addValidators({
     email: (value) => {
       regexp = new RegExp(/^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/);
       if (!regexp.test(value)) {
         throw new Error('Email address is invalid.')
       }
     }
   });

   const ContactSchema = new Schema({
     name: String,
     contact: { type: String, validator: 'email' }
   });
 ```

**Parameters:**

Name | Type |
------ | ------ |
`validators` | [CustomValidations](globals.md#customvalidations) |

**Returns:** *void*

___

### `Const` applyDefaultValue

▸ **applyDefaultValue**(`obj`: any, `schema`: [Schema](classes/schema.md) | [SchemaDef](globals.md#schemadef)): *any*

Apply default values defined on schema to an object instance

**`example`** 
```ts
 const schema = {name: {type: String, default: 'John'}, hasChild: {type: Boolean, default: true}};
 const obj: any = applyDefaultValue(obj, schema)

 console.log(obj);
```

**Parameters:**

Name | Type | Description |
------ | ------ | ------ |
`obj` | any | reference to object instance |
`schema` | [Schema](classes/schema.md) &#124; [SchemaDef](globals.md#schemadef) | definition will be used to determine default definitions  |

**Returns:** *any*

___

### `Const` applyValidator

▸ **applyValidator**(`val`: unknown, `validator`: [ValidatorOption](interfaces/validatoroption.md) | [ValidatorFunction](globals.md#validatorfunction) | string | undefined, `name?`: undefined | string): *string | void*

**Parameters:**

Name | Type |
------ | ------ |
`val` | unknown |
`validator` | [ValidatorOption](interfaces/validatoroption.md) &#124; [ValidatorFunction](globals.md#validatorfunction) &#124; string &#124; undefined |
`name?` | undefined &#124; string |

**Returns:** *string | void*

___

### `Const` arrayDiff

▸ **arrayDiff**(`arr1`: any, `arr2`: any): *any*

**Parameters:**

Name | Type |
------ | ------ |
`arr1` | any |
`arr2` | any |

**Returns:** *any*

___

### `Const` arrayTypeFactory

▸ **arrayTypeFactory**(`name`: string, `item`: [CoreType](classes/coretype.md)): *[ArrayType](classes/arraytype.md)*

**Parameters:**

Name | Type |
------ | ------ |
`name` | string |
`item` | [CoreType](classes/coretype.md) |

**Returns:** *[ArrayType](classes/arraytype.md)*

___

### `Const` booleanTypeFactory

▸ **booleanTypeFactory**(`key`: string, `opts`: [CoreTypeOptions](interfaces/coretypeoptions.md)): *[BooleanType](classes/booleantype.md)*

**Parameters:**

Name | Type |
------ | ------ |
`key` | string |
`opts` | [CoreTypeOptions](interfaces/coretypeoptions.md) |

**Returns:** *[BooleanType](classes/booleantype.md)*

___

### `Const` buildFields

▸ **buildFields**(`obj`: [Schema](classes/schema.md) | [SchemaDef](globals.md#schemadef), `strategy?`: [VALIDATION_STRATEGY](enums/validation_strategy.md)): *[FieldMap](globals.md#fieldmap)*

Build the fields using the given definition. If the [[obj]] is a schema instance, the data will be taken from the fields provided

**`function`** 

**`throws`** {Error}

**`example`** 
 ```ts
   const fields = buildFields({name: String, hasChild: {type: Boolean, default: true}});
 ```

**Parameters:**

Name | Type | Description |
------ | ------ | ------ |
`obj` | [Schema](classes/schema.md) &#124; [SchemaDef](globals.md#schemadef) | the definition or schema instance |
`strategy?` | [VALIDATION_STRATEGY](enums/validation_strategy.md) | define validation policy |

**Returns:** *[FieldMap](globals.md#fieldmap)*

___

### `Const` buildFieldsRefKey

▸ **buildFieldsRefKey**(`fields`: string[], `prefix`: string): *string*

**Parameters:**

Name | Type |
------ | ------ |
`fields` | string[] |
`prefix` | string |

**Returns:** *string*

___

### `Const` buildIndexExpr

▸ **buildIndexExpr**(`collection`: string, `type`: [IndexType](globals.md#indextype), `name`: string, `on?`: [IIndexOnParams](interfaces/iindexonparams.md)[], `where?`: [LogicalWhereExpr](globals.md#logicalwhereexpr), `usingGSI?`: undefined | false | true, `withExpr?`: [IIndexWithParams](interfaces/iindexwithparams.md)): *string*

Build a INDEX N1QL query from user-specified parameters.
[https://docs.couchbase.com/server/6.5/n1ql/n1ql-language-reference/createindex.html](https://docs.couchbase.com/server/6.5/n1ql/n1ql-language-reference/createindex.html)

**Parameters:**

Name | Type | Description |
------ | ------ | ------ |
`collection` | string | Collection name |
`type` | [IndexType](globals.md#indextype) | INDEX clause types can be 'CREATE' | 'BUILD' | 'DROP' | 'CREATE PRIMARY' |
`name` | string | - |
`on?` | [IIndexOnParams](interfaces/iindexonparams.md)[] | ON Clause param |
`where?` | [LogicalWhereExpr](globals.md#logicalwhereexpr) | WHERE Clause param |
`usingGSI?` | undefined &#124; false &#124; true | use a Global Secondary Index(GSI). |
`withExpr?` | [IIndexWithParams](interfaces/iindexwithparams.md) | WITH Clause param  |

**Returns:** *string*

N1QL INDEX Query

___

### `Const` buildIndexQuery

▸ **buildIndexQuery**(`Model`: any, `fields`: any, `indexFnName`: any, `indexOptions`: object): *(Anonymous function)*

View index function factory

**Parameters:**

Name | Type | Default |
------ | ------ | ------ |
`Model` | any | - |
`fields` | any | - |
`indexFnName` | any | - |
`indexOptions` | object | {} |

**Returns:** *(Anonymous function)*

___

### `Const` buildMapViewIndexFn

▸ **buildMapViewIndexFn**(`metadata`: [ModelMetadata](interfaces/modelmetadata.md), `fields`: any): *string*

**Parameters:**

Name | Type |
------ | ------ |
`metadata` | [ModelMetadata](interfaces/modelmetadata.md) |
`fields` | any |

**Returns:** *string*

___

### `Const` buildRefKey

▸ **buildRefKey**(`fields`: string[], `values`: string[], `prefix`: string): *string*

**Parameters:**

Name | Type |
------ | ------ |
`fields` | string[] |
`values` | string[] |
`prefix` | string |

**Returns:** *string*

___

### `Const` buildSelectArrayExpr

▸ **buildSelectArrayExpr**(`clause`: [ISelectType](globals.md#iselecttype)[]): *string*

Create N1QL queries from select array params

**Parameters:**

Name | Type | Description |
------ | ------ | ------ |
`clause` | [ISelectType](globals.md#iselecttype)[] | SELECT Clause param  |

**Returns:** *string*

N1QL SELECT Query

___

### `Const` buildSelectExpr

▸ **buildSelectExpr**(`n1ql`: string, `clause`: [ISelectType](globals.md#iselecttype)): *string*

Recursive function to create N1QL queries.

**Parameters:**

Name | Type | Description |
------ | ------ | ------ |
`n1ql` | string | N1QL Query String |
`clause` | [ISelectType](globals.md#iselecttype) | SELECT Clause param  |

**Returns:** *string*

N1QL SELECT Query

___

### `Const` buildViewIndexQuery

▸ **buildViewIndexQuery**(`connection`: any, `ddocName`: any, `indexName`: any, `fields`: any, `Model`: any): *(Anonymous function)*

Index function factory

**Parameters:**

Name | Type |
------ | ------ |
`connection` | any |
`ddocName` | any |
`indexName` | any |
`fields` | any |
`Model` | any |

**Returns:** *(Anonymous function)*

___

### `Const` buildViewRefdoc

▸ **buildViewRefdoc**(`metadata`: [ModelMetadata](interfaces/modelmetadata.md), `Model`: any, `fields`: any, `prefix`: any): *(Anonymous function)*

**Parameters:**

Name | Type |
------ | ------ |
`metadata` | [ModelMetadata](interfaces/modelmetadata.md) |
`Model` | any |
`fields` | any |
`prefix` | any |

**Returns:** *(Anonymous function)*

___

### `Const` buildWhereClauseExpr

▸ **buildWhereClauseExpr**(`n1ql`: string, `clause`: [LogicalWhereExpr](globals.md#logicalwhereexpr)): *string*

Recursive function to create WHERE N1QL Expressions.

**Parameters:**

Name | Type | Description |
------ | ------ | ------ |
`n1ql` | string | N1QL Query String |
`clause` | [LogicalWhereExpr](globals.md#logicalwhereexpr) | WHERE Clause param  |

**Returns:** *string*

N1QL WHERE Expression

___

### `Const` buildWhereExpr

▸ **buildWhereExpr**(`expr`: [LogicalWhereExpr](globals.md#logicalwhereexpr) | undefined, `clause?`: undefined | string): *string*

Create WHERE N1QL Expressions.
[https://docs.couchbase.com/server/6.5/n1ql/n1ql-language-reference/where.html](https://docs.couchbase.com/server/6.5/n1ql/n1ql-language-reference/where.html)

**Parameters:**

Name | Type | Description |
------ | ------ | ------ |
`expr` | [LogicalWhereExpr](globals.md#logicalwhereexpr) &#124; undefined | - |
`clause?` | undefined &#124; string | WHERE Clause param |

**Returns:** *string*

N1QL WHERE Expression

___

### `Const` canBePopulated

▸ **canBePopulated**(`populate`: string, `fields`: string[]): *boolean*

Determine if a given field can be populated.

**Parameters:**

Name | Type |
------ | ------ |
`populate` | string |
`fields` | string[] |

**Returns:** *boolean*

___

### `Const` castSchema

▸ **castSchema**(`data`: any, `schema`: [Schema](classes/schema.md) | [SchemaDef](globals.md#schemadef)): *any*

Validate data using the schema definition

**`throws`** BuildSchemaError, ValidationError

**`example`** 
```ts
   const data = {
     name: "John",
     age: "50"
   };
   const schema = new Schema({
     name: String,
     age: {type: Number, intVal: true}
   });
   const strictSchema = new Schema({
     name: String,
     age: {type: Number, intVal: true}
    },
    {
     validationStrategy: VALIDATION_STRATEGY.STRICT
    });
   console.log(castSchema(data, schema)); // Print {name: "John", age: 50}
   console.log(castSchema(data, strictSchema)); // Throw "Property age must be of type Number"
```

**Parameters:**

Name | Type | Description |
------ | ------ | ------ |
`data` | any | that is going to be validated |
`schema` | [Schema](classes/schema.md) &#124; [SchemaDef](globals.md#schemadef) | that will be used to validate |

**Returns:** *any*

___

### `Const` connectFromEnvVariables

▸ **connectFromEnvVariables**(`modelName`: string): *void*

Allow connecting from env variable OTTOMAN_CONNECTION_STRING if provided.

**Parameters:**

Name | Type |
------ | ------ |
`modelName` | string |

**Returns:** *void*

___

### `Const` dateTypeFactory

▸ **dateTypeFactory**(`name`: string, `opts`: [DateTypeOptions](interfaces/datetypeoptions.md) & [CoreTypeOptions](interfaces/coretypeoptions.md)): *[DateType](classes/datetype.md)*

**Parameters:**

Name | Type |
------ | ------ |
`name` | string |
`opts` | [DateTypeOptions](interfaces/datetypeoptions.md) & [CoreTypeOptions](interfaces/coretypeoptions.md) |

**Returns:** *[DateType](classes/datetype.md)*

___

### `Const` delay

▸ **delay**(`timems`: any): *Promise‹unknown›*

**Parameters:**

Name | Type |
------ | ------ |
`timems` | any |

**Returns:** *Promise‹unknown›*

___

### `Const` embedTypeFactory

▸ **embedTypeFactory**(`name`: string, `schema`: [Schema](classes/schema.md)): *[EmbedType](classes/embedtype.md)*

**Parameters:**

Name | Type |
------ | ------ |
`name` | string |
`schema` | [Schema](classes/schema.md) |

**Returns:** *[EmbedType](classes/embedtype.md)*

___

### `Const` ensureIndexes

▸ **ensureIndexes**(`connection?`: [ConnectionManager](classes/connectionmanager.md)): *Promise‹void›*

Ensure that all indexes are created in the server

**Parameters:**

Name | Type |
------ | ------ |
`connection?` | [ConnectionManager](classes/connectionmanager.md) |

**Returns:** *Promise‹void›*

___

### `Const` ensureN1qlIndexes

▸ **ensureN1qlIndexes**(`connection`: [ConnectionManager](classes/connectionmanager.md)): *Promise‹any›*

Creates the register index in the Database Server.
In addition, creates one index as primary for the bucketName
and one for every Ottoman model.

**Parameters:**

Name | Type |
------ | ------ |
`connection` | [ConnectionManager](classes/connectionmanager.md) |

**Returns:** *Promise‹any›*

___

### `Const` ensureViewIndexes

▸ **ensureViewIndexes**(`connection`: [ConnectionManager](classes/connectionmanager.md)): *Promise‹undefined | true›*

**Parameters:**

Name | Type |
------ | ------ |
`connection` | [ConnectionManager](classes/connectionmanager.md) |

**Returns:** *Promise‹undefined | true›*

___

### `Const` execHooks

▸ **execHooks**(`schema`: any, `hookType`: "preHooks" | "postHooks", `hookAction`: any, `document?`: any): *Promise‹void›*

Allows to execute hooks in chain,
passing the previous result value to the next hook.

**Parameters:**

Name | Type |
------ | ------ |
`schema` | any |
`hookType` | "preHooks" &#124; "postHooks" |
`hookAction` | any |
`document?` | any |

**Returns:** *Promise‹void›*

___

### `Const` execPopulation

▸ **execPopulation**(`rows`: any, `toPopulate`: string, `connection`: any, `modelName`: string, `deep?`: any): *Promise‹any[]›*

Populate a given field through an array with references.

**Parameters:**

Name | Type |
------ | ------ |
`rows` | any |
`toPopulate` | string |
`connection` | any |
`modelName` | string |
`deep?` | any |

**Returns:** *Promise‹any[]›*

___

### `Const` extractConnectionString

▸ **extractConnectionString**(`connectOptions`: string): *[ConnectOptions](interfaces/connectoptions.md)*

**Parameters:**

Name | Type |
------ | ------ |
`connectOptions` | string |

**Returns:** *[ConnectOptions](interfaces/connectoptions.md)*

___

### `Const` extractDataFromModel

▸ **extractDataFromModel**(`document`: any): *any*

Get a Model instance and return a javascript Object

**Parameters:**

Name | Type |
------ | ------ |
`document` | any |

**Returns:** *any*

___

### `Const` extractIndexFieldNames

▸ **extractIndexFieldNames**(`gsi`: object): *string[]*

**Parameters:**

▪ **gsi**: *object*

Name | Type |
------ | ------ |
`fields` | string[] |

**Returns:** *string[]*

___

### `Const` extractPopulate

▸ **extractPopulate**(`populate`: FindOptions["populate"]): *string[]*

Extract the values to be populated.

**Parameters:**

Name | Type |
------ | ------ |
`populate` | FindOptions["populate"] |

**Returns:** *string[]*

___

### `Const` extractSchemaReferencesFields

▸ **extractSchemaReferencesFields**(`schema`: [Schema](classes/schema.md)): *any*

**Parameters:**

Name | Type |
------ | ------ |
`schema` | [Schema](classes/schema.md) |

**Returns:** *any*

___

### `Const` extractSchemaReferencesFromGivenFields

▸ **extractSchemaReferencesFromGivenFields**(`fields`: any, `schema`: [Schema](classes/schema.md)): *any*

**Parameters:**

Name | Type |
------ | ------ |
`fields` | any |
`schema` | [Schema](classes/schema.md) |

**Returns:** *any*

___

### `Const` extractSelect

▸ **extractSelect**(`select`: string | string[], `options`: object, `excludeMeta`: boolean): *string[]*

**Parameters:**

▪ **select**: *string | string[]*

▪`Default value`  **options**: *object*= {}

Name | Type |
------ | ------ |
`noCollection?` | undefined &#124; false &#124; true |

▪`Default value`  **excludeMeta**: *boolean*= false

**Returns:** *string[]*

___

### `Const` generateUUID

▸ **generateUUID**(): *any*

**Returns:** *any*

___

### `Const` getCollectionKey

▸ **getCollectionKey**(): *string*

**Returns:** *string*

▸ **getCollectionKey**(): *string*

**Returns:** *string*

___

### `Const` getGlobalPlugins

▸ **getGlobalPlugins**(): *function[]*

Return all global plugins

**Returns:** *function[]*

___

### `Const` getIndexes

▸ **getIndexes**(): *object*

Returns all indexes

**Returns:** *object*

___

### `Const` getMetadata

▸ **getMetadata**(`noCollection?`: undefined | false | true): *string[]*

**Parameters:**

Name | Type |
------ | ------ |
`noCollection?` | undefined &#124; false &#124; true |

**Returns:** *string[]*

___

### `Const` getModelMetadata

▸ **getModelMetadata**(`modelConstructor`: any): *any*

**Parameters:**

Name | Type |
------ | ------ |
`modelConstructor` | any |

**Returns:** *any*

___

### `Const` getModelRefKeys

▸ **getModelRefKeys**(`data`: any, `prefix`: any): *string[]*

**Parameters:**

Name | Type |
------ | ------ |
`data` | any |
`prefix` | any |

**Returns:** *string[]*

___

### `Const` getProjectionFields

▸ **getProjectionFields**(`collection`: string, `select`: [ISelectType](globals.md#iselecttype)[] | string | string[], `options`: object): *object*

**Parameters:**

▪ **collection**: *string*

▪`Default value`  **select**: *[ISelectType](globals.md#iselecttype)[] | string | string[]*= ""

▪`Default value`  **options**: *object*= {}

Name | Type |
------ | ------ |
`noCollection?` | undefined &#124; false &#124; true |

**Returns:** *object*

* **fields**: *string[]*

* **projection**: *string*

___

### `Const` getRefdocIndexByKey

▸ **getRefdocIndexByKey**(`key`: any): *object[]*

**Parameters:**

Name | Type |
------ | ------ |
`key` | any |

**Returns:** *object[]*

___

### `Const` getRefdocIndexes

▸ **getRefdocIndexes**(): *object*

**Returns:** *object*

___

### `Const` getSchemaType

▸ **getSchemaType**(`fieldName`: any, `schema`: any): *any*

**Parameters:**

Name | Type |
------ | ------ |
`fieldName` | any |
`schema` | any |

**Returns:** *any*

___

### `Const` getScopeKey

▸ **getScopeKey**(): *string*

**Returns:** *string*

___

### `Const` getViewIndexes

▸ **getViewIndexes**(): *object*

**Returns:** *object*

___

### `Const` globalConfig

▸ **globalConfig**(`__namedParameters`: object): *void*

**Parameters:**

▪`Default value`  **__namedParameters**: *object*= {}

Name | Type |
------ | ------ |
`collectionKey` | undefined &#124; string |
`defaultScope` | undefined &#124; string |
`disableScopes` | undefined &#124; false &#124; true |
`keyGenerator` | undefined &#124; function |
`populateMaxDeep` | undefined &#124; number |
`scopeKey` | undefined &#124; string |

**Returns:** *void*

___

### `Const` hasIndex

▸ **hasIndex**(`indexName`: string): *boolean*

Receives an index name and return if it is already registered

**Parameters:**

Name | Type |
------ | ------ |
`indexName` | string |

**Returns:** *boolean*

___

### `Const` indexFieldsName

▸ **indexFieldsName**(`fields`: string[]): *string*

**Parameters:**

Name | Type |
------ | ------ |
`fields` | string[] |

**Returns:** *string*

___

### `Const` is

▸ **is**(`val`: any, `type`: any): *boolean*

Checking if a value is a specific type or constructor

**Parameters:**

Name | Type | Description |
------ | ------ | ------ |
`val` | any | - |
`type` | any |   |

**Returns:** *boolean*

___

### `Const` isDebugMode

▸ **isDebugMode**(): *boolean*

**Returns:** *boolean*

___

### `Const` isDocumentNotFoundError

▸ **isDocumentNotFoundError**(`exception`: any): *boolean*

Return a boolean value if an exception is DocumentNotFoundError

**Parameters:**

Name | Type |
------ | ------ |
`exception` | any |

**Returns:** *boolean*

___

### `Const` isMetadataKey

▸ **isMetadataKey**(`key`: string): *boolean*

**Parameters:**

Name | Type |
------ | ------ |
`key` | string |

**Returns:** *boolean*

___

### `Const` isModel

▸ **isModel**(`model`: any): *boolean*

**Parameters:**

Name | Type |
------ | ------ |
`model` | any |

**Returns:** *boolean*

___

### `Const` isOttomanType

▸ **isOttomanType**(`object`: any): *boolean*

**Parameters:**

Name | Type |
------ | ------ |
`object` | any |

**Returns:** *boolean*

___

### `Const` jpParse

▸ **jpParse**(`pathStr`: string): *any*

**Parameters:**

Name | Type |
------ | ------ |
`pathStr` | string |

**Returns:** *any*

___

### `Const` nonenumerable

▸ **nonenumerable**(`target`: any, `propertyKey`: string): *void*

Set a given property of the target to be no-enumerable
Will not be listed on Object.keys and will be excluded by spread operator

**Parameters:**

Name | Type |
------ | ------ |
`target` | any |
`propertyKey` | string |

**Returns:** *void*

___

### `Const` numberTypeFactory

▸ **numberTypeFactory**(`name`: string, `otps`: [CoreTypeOptions](interfaces/coretypeoptions.md) & [NumberTypeOptions](interfaces/numbertypeoptions.md)): *[NumberType](classes/numbertype.md)*

**Parameters:**

Name | Type |
------ | ------ |
`name` | string |
`otps` | [CoreTypeOptions](interfaces/coretypeoptions.md) & [NumberTypeOptions](interfaces/numbertypeoptions.md) |

**Returns:** *[NumberType](classes/numbertype.md)*

___

### `Const` parseStringSelectExpr

▸ **parseStringSelectExpr**(`expr`: string): *string[]*

Convert select expression into an Array of selection keys

**Parameters:**

Name | Type |
------ | ------ |
`expr` | string |

**Returns:** *string[]*

___

### `Const` pathToN1QL

▸ **pathToN1QL**(`path`: any): *string*

**Parameters:**

Name | Type |
------ | ------ |
`path` | any |

**Returns:** *string*

___

### `Const` pipe

▸ **pipe**(...`fns`: any[]): *(Anonymous function)*

Performs left-to-right function composition for asynchronous functions.

**Parameters:**

Name | Type |
------ | ------ |
`...fns` | any[] |

**Returns:** *(Anonymous function)*

___

### `Const` queryBuildIndexDefered

▸ **queryBuildIndexDefered**(`bucketName`: any, `indexName`: any, `fields`: any, `metadata`: [ModelMetadata](interfaces/modelmetadata.md)): *string*

**Parameters:**

Name | Type |
------ | ------ |
`bucketName` | any |
`indexName` | any |
`fields` | any |
`metadata` | [ModelMetadata](interfaces/modelmetadata.md) |

**Returns:** *string*

___

### `Const` queryBuildIndexes

▸ **queryBuildIndexes**(`bucketName`: any, `indexesName`: string[]): *string*

**Parameters:**

Name | Type |
------ | ------ |
`bucketName` | any |
`indexesName` | string[] |

**Returns:** *string*

___

### `Const` queryForIndexOttomanType

▸ **queryForIndexOttomanType**(`bucketName`: any, `ottomanType`: any): *string*

**Parameters:**

Name | Type |
------ | ------ |
`bucketName` | any |
`ottomanType` | any |

**Returns:** *string*

___

### `Const` queryForPrimaryIndex

▸ **queryForPrimaryIndex**(`bucketName`: any): *string*

**Parameters:**

Name | Type |
------ | ------ |
`bucketName` | any |

**Returns:** *string*

___

### `Const` referenceTypeFactory

▸ **referenceTypeFactory**(`name`: string, `opts`: [ReferenceOptions](interfaces/referenceoptions.md)): *[ReferenceType](classes/referencetype.md)*

**Parameters:**

Name | Type |
------ | ------ |
`name` | string |
`opts` | [ReferenceOptions](interfaces/referenceoptions.md) |

**Returns:** *[ReferenceType](classes/referencetype.md)*

___

### `Const` registerGlobalPlugin

▸ **registerGlobalPlugin**(...`plugins`: any[]): *void*

Register a global plugin.

**Parameters:**

Name | Type |
------ | ------ |
`...plugins` | any[] |

**Returns:** *void*

___

### `Const` registerIndex

▸ **registerIndex**(`indexName`: string, `fields`: any, `modelName`: any): *void*

Registers a new index

**Parameters:**

Name | Type |
------ | ------ |
`indexName` | string |
`fields` | any |
`modelName` | any |

**Returns:** *void*

___

### `Const` registerRefdocIndex

▸ **registerRefdocIndex**(`fields`: string[], `prefix`: string): *void*

**Parameters:**

Name | Type |
------ | ------ |
`fields` | string[] |
`prefix` | string |

**Returns:** *void*

___

### `Const` registerType

▸ **registerType**(`name`: string, `factory`: [FactoryFunction](globals.md#factoryfunction)): *void*

Register a custom type to Schema supported types.

**`function`** 

**`throws`** Error

**`example`** 
 ```ts
   registerType(Int8.name, (fieldName, opts) => new Int8(fieldName, opts.required));
 ```

**Parameters:**

Name | Type |
------ | ------ |
`name` | string |
`factory` | [FactoryFunction](globals.md#factoryfunction) |

**Returns:** *void*

___

### `Const` registerViewIndex

▸ **registerViewIndex**(`ddocName`: string, `indexName`: string, `fields`: any, `metadata`: any): *void*

**Parameters:**

Name | Type |
------ | ------ |
`ddocName` | string |
`indexName` | string |
`fields` | any |
`metadata` | any |

**Returns:** *void*

___

### `Const` remove

▸ **remove**(`id`: any, `collection`: any, `options?`: [RemoveOptions](interfaces/removeoptions.md)): *Promise‹any›*

Remove a document by id from the given collection

**Parameters:**

Name | Type |
------ | ------ |
`id` | any |
`collection` | any |
`options?` | [RemoveOptions](interfaces/removeoptions.md) |

**Returns:** *Promise‹any›*

___

###  removeRefKeys

▸ **removeRefKeys**(`refKeys`: any, `collection`: any): *AsyncGenerator‹any, void, unknown›*

**Parameters:**

Name | Type |
------ | ------ |
`refKeys` | any |
`collection` | any |

**Returns:** *AsyncGenerator‹any, void, unknown›*

___

### `Const` selectBuilder

▸ **selectBuilder**(`collection`: string, `select`: [ISelectType](globals.md#iselecttype)[] | string, `letExpr?`: [ILetExpr](interfaces/iletexpr.md)[], `where?`: [LogicalWhereExpr](globals.md#logicalwhereexpr), `orderBy?`: Record‹string, [SortType](globals.md#sorttype)›, `limit?`: undefined | number, `offset?`: undefined | number, `useExpr?`: string[], `groupByExpr?`: [IGroupBy](interfaces/igroupby.md)[], `lettingExpr?`: [ILetExpr](interfaces/iletexpr.md)[], `havingExpr?`: [LogicalWhereExpr](globals.md#logicalwhereexpr), `plainJoinExpr?`: undefined | string): *string*

Build a SELECT N1QL query from user-specified parameters.
[https://docs.couchbase.com/server/6.5/n1ql/n1ql-language-reference/select-syntax.html](https://docs.couchbase.com/server/6.5/n1ql/n1ql-language-reference/select-syntax.html)

**Parameters:**

Name | Type | Description |
------ | ------ | ------ |
`collection` | string | Collection name |
`select` | [ISelectType](globals.md#iselecttype)[] &#124; string | SELECT Clause param |
`letExpr?` | [ILetExpr](interfaces/iletexpr.md)[] | LET Clause param |
`where?` | [LogicalWhereExpr](globals.md#logicalwhereexpr) | WHERE Clause param |
`orderBy?` | Record‹string, [SortType](globals.md#sorttype)› | ORDER BY Clause param |
`limit?` | undefined &#124; number | LIMIT Clause param |
`offset?` | undefined &#124; number | OFFSET Clause param |
`useExpr?` | string[] | USE Clause param  |
`groupByExpr?` | [IGroupBy](interfaces/igroupby.md)[] | - |
`lettingExpr?` | [ILetExpr](interfaces/iletexpr.md)[] | - |
`havingExpr?` | [LogicalWhereExpr](globals.md#logicalwhereexpr) | - |
`plainJoinExpr?` | undefined &#124; string | - |

**Returns:** *string*

N1QL SELECT Query

___

### `Const` setModelMetadata

▸ **setModelMetadata**(`modelConstructor`: any, `metadata`: [ModelMetadata](interfaces/modelmetadata.md)): *[ModelMetadata](interfaces/modelmetadata.md)*

**Parameters:**

Name | Type |
------ | ------ |
`modelConstructor` | any |
`metadata` | [ModelMetadata](interfaces/modelmetadata.md) |

**Returns:** *[ModelMetadata](interfaces/modelmetadata.md)*

___

### `Const` store

▸ **store**(`key`: any, `data`: any, `options`: [StoreOptions](interfaces/storeoptions.md), `collection`: any): *Promise‹any›*

 Store a Document
 if cas value is defined then the document is updated, otherwise it is inserted.

**Parameters:**

Name | Type |
------ | ------ |
`key` | any |
`data` | any |
`options` | [StoreOptions](interfaces/storeoptions.md) |
`collection` | any |

**Returns:** *Promise‹any›*

___

### `Const` stringTypeFactory

▸ **stringTypeFactory**(`key`: string, `opts`: [StringTypeOptions](interfaces/stringtypeoptions.md) & [CoreTypeOptions](interfaces/coretypeoptions.md)): *[StringType](classes/stringtype.md)*

**Parameters:**

Name | Type |
------ | ------ |
`key` | string |
`opts` | [StringTypeOptions](interfaces/stringtypeoptions.md) & [CoreTypeOptions](interfaces/coretypeoptions.md) |

**Returns:** *[StringType](classes/stringtype.md)*

___

### `Const` stringifyValues

▸ **stringifyValues**(`value`: unknown): *string*

**Parameters:**

Name | Type |
------ | ------ |
`value` | unknown |

**Returns:** *string*

___

### `Const` updateRefdocIndexes

▸ **updateRefdocIndexes**(`refKeys`: object, `key`: string | null, `collection`: any): *Promise‹void›*

**Parameters:**

▪ **refKeys**: *object*

Name | Type |
------ | ------ |
`add` | string[] |
`remove` | string[] |

▪ **key**: *string | null*

▪ **collection**: *any*

**Returns:** *Promise‹void›*

___

### `Const` validateMaxDate

▸ **validateMaxDate**(`value`: Date, `max`: Date | [DateOption](interfaces/dateoption.md)): *string | void*

**Parameters:**

Name | Type |
------ | ------ |
`value` | Date |
`max` | Date &#124; [DateOption](interfaces/dateoption.md) |

**Returns:** *string | void*

___

### `Const` validateMaxLimit

▸ **validateMaxLimit**(`val`: number, `max`: number | [MinmaxOption](interfaces/minmaxoption.md) | undefined): *string | void*

**Parameters:**

Name | Type |
------ | ------ |
`val` | number |
`max` | number &#124; [MinmaxOption](interfaces/minmaxoption.md) &#124; undefined |

**Returns:** *string | void*

___

### `Const` validateMinDate

▸ **validateMinDate**(`value`: Date, `min`: Date | [DateOption](interfaces/dateoption.md)): *string | void*

**Parameters:**

Name | Type |
------ | ------ |
`value` | Date |
`min` | Date &#124; [DateOption](interfaces/dateoption.md) |

**Returns:** *string | void*

___

### `Const` validateMinLimit

▸ **validateMinLimit**(`val`: number, `min`: number | [MinmaxOption](interfaces/minmaxoption.md) | undefined): *string | void*

**Parameters:**

Name | Type |
------ | ------ |
`val` | number |
`min` | number &#124; [MinmaxOption](interfaces/minmaxoption.md) &#124; undefined |

**Returns:** *string | void*

## Object literals

### `Const` AggDict

### ▪ **AggDict**: *object*

Dictionary for handling aggregation functions.

###  $arrayAgg

• **$arrayAgg**: *string* = "ARRAY_AGG"

###  $avg

• **$avg**: *string* = "AVG"

###  $count

• **$count**: *string* = "COUNT"

###  $countn

• **$countn**: *string* = "COUNTN"

###  $max

• **$max**: *string* = "MAX"

###  $mean

• **$mean**: *string* = "MEAN"

###  $median

• **$median**: *string* = "MEDIAN"

###  $min

• **$min**: *string* = "MIN"

###  $stddev

• **$stddev**: *string* = "STDDEV"

###  $stddevPop

• **$stddevPop**: *string* = "STDDEV_POP"

###  $stddevSamp

• **$stddevSamp**: *string* = "STDDEV_SAMP"

###  $sum

• **$sum**: *string* = "SUM"

###  $varPop

• **$varPop**: *string* = "VAR_POP"

###  $varSamp

• **$varSamp**: *string* = "VAR_SAMP"

###  $variance

• **$variance**: *string* = "VARIANCE"

###  $variancePop

• **$variancePop**: *string* = "VARIANCE_POP"

###  $varianceSamp

• **$varianceSamp**: *string* = "VARIANCE_SAMP"

___

### `Const` CollectionInWithinOperatorDict

### ▪ **CollectionInWithinOperatorDict**: *object*

Dictionary for handling collection (in | within) operators

###  $in

• **$in**: *string* = "IN"

###  $within

• **$within**: *string* = "WITHIN"

___

### `Const` CollectionSatisfiesOperatorDict

### ▪ **CollectionSatisfiesOperatorDict**: *object*

Dictionary for handling collection satisfies operators

###  $satisfies

• **$satisfies**: *string* = "SATISFIES"

___

### `Const` CollectionSelectOperatorDict

### ▪ **CollectionSelectOperatorDict**: *object*

Dictionary for handling collection select operators

###  $any

• **$any**: *string* = "ANY"

###  $every

• **$every**: *string* = "EVERY"

___

### `Const` ComparisonEmptyOperatorDict

### ▪ **ComparisonEmptyOperatorDict**: *object*

Dictionary for handling Boolean comparison operators

###  $isMissing

• **$isMissing**: *string* = "IS MISSING"

###  $isNotMissing

• **$isNotMissing**: *string* = "IS NOT MISSING"

###  $isNotNull

• **$isNotNull**: *string* = "IS NOT NULL"

###  $isNotValued

• **$isNotValued**: *string* = "IS NOT VALUED"

###  $isNull

• **$isNull**: *string* = "IS NULL"

###  $isValued

• **$isValued**: *string* = "IS VALUED"

___

### `Const` ComparisonMultipleOperatorDict

### ▪ **ComparisonMultipleOperatorDict**: *object*

Dictionary for handling Range comparison operators

###  $btw

• **$btw**: *string* = "BETWEEN"

###  $notBtw

• **$notBtw**: *string* = "NOT BETWEEN"

___

### `Const` ComparisonSingleOperatorDict

### ▪ **ComparisonSingleOperatorDict**: *object*

Dictionary for handling Numeric comparison operators

###  $eq

• **$eq**: *string* = "="

###  $gt

• **$gt**: *string* = ">"

###  $gte

• **$gte**: *string* = ">="

###  $lt

• **$lt**: *string* = "<"

###  $lte

• **$lte**: *string* = "<="

###  $neq

• **$neq**: *string* = "!="

___

### `Const` ComparisonSingleStringOperatorDict

### ▪ **ComparisonSingleStringOperatorDict**: *object*

Dictionary for handling String comparison operators

###  $like

• **$like**: *string* = "LIKE"

###  $notLike

• **$notLike**: *string* = "NOT LIKE"

___

### `Const` LogicalOperatorDict

### ▪ **LogicalOperatorDict**: *object*

Dictionary for handling logical operators

###  $and

• **$and**: *string* = "AND"

###  $not

• **$not**: *string* = "NOT"

###  $or

• **$or**: *string* = "OR"

___

### `Const` ResultExprDict

### ▪ **ResultExprDict**: *object*

Dictionary for handling result expressions RAW | ELEMENT | VALUE

###  $element

• **$element**: *string* = "ELEMENT"

###  $raw

• **$raw**: *string* = "RAW"

###  $value

• **$value**: *string* = "VALUE"

___

### `Const` ReturnResultDict

### ▪ **ReturnResultDict**: *object*

Dictionary for handling result expressions ALL | DISTINCT

###  $all

• **$all**: *string* = "ALL"

###  $distinct

• **$distinct**: *string* = "DISTINCT"
