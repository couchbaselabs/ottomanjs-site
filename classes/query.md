# Class: Query

## Hierarchy

* [BaseQuery](basequery.md)

  ↳ **Query**

## Constructors

###  constructor

\+ **new Query**(`conditions`: [IConditionExpr](../interfaces/iconditionexpr.md), `collection`: string): *[Query](query.md)*

*Overrides [BaseQuery](basequery.md).[constructor](basequery.md#protected-constructor)*

**`summary`** Create an instance of Query.

**`name`** Query

**`example`** 
```ts
 const query = new Query({$select: [{$field: 'address'}], $where: {$nill: [{ address: { $like: '%57-59%' } }, { free_breakfast: true }, { free_lunch: [1] }]}}, 'travel-sample');
```

**Parameters:**

Name | Type | Description |
------ | ------ | ------ |
`conditions` | [IConditionExpr](../interfaces/iconditionexpr.md) | List of SELECT clause conditions |
`collection` | string | Collection name |

**Returns:** *[Query](query.md)*

Query

## Properties

### `Protected` _collection

• **_collection**: *string*

*Inherited from [BaseQuery](basequery.md).[_collection](basequery.md#protected-_collection)*

___

### `Protected` _conditions

• **_conditions**: *[IConditionExpr](../interfaces/iconditionexpr.md)*

*Inherited from [BaseQuery](basequery.md).[_conditions](basequery.md#protected-_conditions)*

## Accessors

###  collection

• **get collection**(): *string*

**Returns:** *string*

• **set collection**(`value`: string): *void*

**Parameters:**

Name | Type |
------ | ------ |
`value` | string |

**Returns:** *void*

___

###  conditions

• **get conditions**(): *[IConditionExpr](../interfaces/iconditionexpr.md)*

**Returns:** *[IConditionExpr](../interfaces/iconditionexpr.md)*

• **set conditions**(`value`: [IConditionExpr](../interfaces/iconditionexpr.md)): *void*

**Parameters:**

Name | Type |
------ | ------ |
`value` | [IConditionExpr](../interfaces/iconditionexpr.md) |

**Returns:** *void*

## Methods

###  build

▸ **build**(): *string*

*Overrides [BaseQuery](basequery.md).[build](basequery.md#abstract-build)*

Build a n1ql query from the defined parameters.

**`method`** 

**Returns:** *string*

___

###  compileFromConditions

▸ **compileFromConditions**(`conditionals`: [IConditionExpr](../interfaces/iconditionexpr.md)): *void*

Converts the conditional parameters passed to the constructor to the properties of the N1QL Query.

**`method`** 

**Parameters:**

Name | Type |
------ | ------ |
`conditionals` | [IConditionExpr](../interfaces/iconditionexpr.md) |

**Returns:** *void*

___

###  groupBy

▸ **groupBy**(`value`: [IGroupBy](../interfaces/igroupby.md)[]): *[Query](query.md)*

Add GROUP BY expression to GROUP BY clause.

**`method`** 

**`example`** 
```ts
  const groupByExpr = [{ expr: 'COUNT(amount_val)', as: 'amount' }];
  const query = new Query({}, 'travel-sample');
  const result = query.select([{$field: 'address'}]).groupBy(groupByExpr).build()
  console.log(result)
```
> SELECT address FROM `travel-sample GROUP BY COUNT(amount) AS amount`

**Parameters:**

Name | Type |
------ | ------ |
`value` | [IGroupBy](../interfaces/igroupby.md)[] |

**Returns:** *[Query](query.md)*

___

###  having

▸ **having**(`value`: [LogicalWhereExpr](../globals.md#logicalwhereexpr)): *[Query](query.md)*

Add HAVING expression to GROUP BY clause.

**`method`** 

**`example`** 
```ts
  const groupByExpr = [{ expr: 'COUNT(amount_val)', as: 'amount' }];
  const having = {address: {$like: '%58%'}};
  const query = new Query({}, 'travel-sample');
  const result = query.select([{$field: 'address'}]).groupBy(groupByExpr).having(having).build()
  console.log(result)
```
> SELECT address FROM `travel-sample GROUP BY COUNT(amount) AS amount HAVING address LIKE '%58%'`

**Parameters:**

Name | Type |
------ | ------ |
`value` | [LogicalWhereExpr](../globals.md#logicalwhereexpr) |

**Returns:** *[Query](query.md)*

___

###  index

▸ **index**(`type`: [IndexType](../globals.md#indextype), `name`: string): *[Query](query.md)*

Add index type and name to INDEX clause.

**`method`** 

**`example`** 
```ts
  const result = new Query({}, 'travel-sample').index('DROP', 'travel_sample_id_test').build();
  console.log(result)
```
> DROP INDEX `travel-sample`.`travel_sample_id_test`

**Parameters:**

Name | Type |
------ | ------ |
`type` | [IndexType](../globals.md#indextype) |
`name` | string |

**Returns:** *[Query](query.md)*

___

###  let

▸ **let**(`value`: [ILetExpr](../interfaces/iletexpr.md)[]): *[Query](query.md)*

*Overrides [BaseQuery](basequery.md).[let](basequery.md#abstract-let)*

Add LET expression to SELECT clause.

**`method`** 

**`example`** 
```ts
  const letExpr = [{ key: 'amount_val', value: 10 }];
  const query = new Query({}, 'travel-sample');
  const result = query.select([{$field: 'address'}]).let(letExpr).build()
  console.log(result)
```
> SELECT address FROM `travel-sample LET amount_val = 10`

**Parameters:**

Name | Type |
------ | ------ |
`value` | [ILetExpr](../interfaces/iletexpr.md)[] |

**Returns:** *[Query](query.md)*

___

###  letting

▸ **letting**(`value`: [ILetExpr](../interfaces/iletexpr.md)[]): *[Query](query.md)*

Add LETTING expression to GROUP BY clause.

**`method`** 

**`example`** 
```ts
  const groupByExpr = [{ expr: 'COUNT(amount_val)', as: 'amount' }];
  const letExpr = [{ key: 'amount_val', value: 10 }];
  const query = new Query({}, 'travel-sample');
  const result = query.select([{$field: 'address'}]).groupBy(groupByExpr).let(letExpr).build()
  console.log(result)
```
> SELECT address FROM `travel-sample GROUP BY COUNT(amount) AS amount LETTING amount = 10`

**Parameters:**

Name | Type |
------ | ------ |
`value` | [ILetExpr](../interfaces/iletexpr.md)[] |

**Returns:** *[Query](query.md)*

___

###  limit

▸ **limit**(`value`: number): *[Query](query.md)*

*Overrides [BaseQuery](basequery.md).[limit](basequery.md#abstract-limit)*

Add LIMIT expression to SELECT clause.

**`method`** 

**`example`** 
```ts
  const query = new Query({}, 'travel-sample');
  const result = query.select([{$field: 'address'}]).limit(10).build()
  console.log(result)
```
> SELECT address FROM `travel-sample LIMIT 10`

**Parameters:**

Name | Type |
------ | ------ |
`value` | number |

**Returns:** *[Query](query.md)*

___

###  offset

▸ **offset**(`value`: number): *[Query](query.md)*

*Overrides [BaseQuery](basequery.md).[offset](basequery.md#abstract-offset)*

Add OFFSET expression to SELECT clause.

**`method`** 

**`example`** 
```ts
  const query = new Query({}, 'travel-sample');
  const result = query.select([{$field: 'address'}]).offset(10).build()
  console.log(result)
```
> SELECT address FROM `travel-sample OFFSET 10`

**Parameters:**

Name | Type |
------ | ------ |
`value` | number |

**Returns:** *[Query](query.md)*

___

###  on

▸ **on**(`value`: [IIndexOnParams](../interfaces/iindexonparams.md)[]): *[Query](query.md)*

Add items to ON clause in INDEX clause.

**`method`** 

**`example`** 
```ts
  const on = [{ name: 'travel-sample.callsing', sort: 'ASC' }];
  const result = new Query({}, 'travel-sample').index('CREATE', 'travel_sample_id_test').on(on).build();
  console.log(result)
```
> CREATE INDEX `travel_sample_id_test` ON `travel-sample`(`travel-sample.callsing`['ASC'])

**Parameters:**

Name | Type |
------ | ------ |
`value` | [IIndexOnParams](../interfaces/iindexonparams.md)[] |

**Returns:** *[Query](query.md)*

___

###  orderBy

▸ **orderBy**(`value`: Record‹string, [SortType](../globals.md#sorttype)›): *[Query](query.md)*

*Overrides [BaseQuery](basequery.md).[orderBy](basequery.md#abstract-orderby)*

Add ORDER BY expression to SELECT clause.

**`method`** 

**`example`** 
```ts
  const query = new Query({}, 'travel-sample');
  const result = query.select([{$field: 'address'}]).orderBy({ size: 'DESC' }).build()
  console.log(result)
```
> SELECT address FROM `travel-sample ORDER BY size = 'DESC'`

**Parameters:**

Name | Type |
------ | ------ |
`value` | Record‹string, [SortType](../globals.md#sorttype)› |

**Returns:** *[Query](query.md)*

___

###  plainJoin

▸ **plainJoin**(`value`: string): *[Query](query.md)*

Add JOIN expression to SELECT clause.

**`method`** 

**`example`** 
```tS
  const query = new Query({}, 'beer-sample brewery');
  const result = query.select([{$field: 'address'}]).plainJoin('JOIN `beer-sample` beer ON beer.brewery_id = LOWER(REPLACE(brewery.name, " ", "_"))').build()
  console.log(result)
```
> SELECT address FROM `beer-sample brewery` JOIN `beer-sample` beer ON beer.brewery_id = LOWER(REPLACE(brewery.name, " ", "_")) LIMIT 1`

**Parameters:**

Name | Type |
------ | ------ |
`value` | string |

**Returns:** *[Query](query.md)*

___

###  select

▸ **select**(`value?`: [ISelectType](../globals.md#iselecttype)[] | string | undefined): *[Query](query.md)*

*Overrides [BaseQuery](basequery.md).[select](basequery.md#abstract-select)*

Add result selectors to SELECT clause.

**`method`** 

**`example`** 
```ts
  const query = new Query({}, 'travel-sample');
  const result = query.select([{$field: 'address'}]).build()
  console.log(result)
```
> SELECT address FROM `travel-sample`

**Parameters:**

Name | Type |
------ | ------ |
`value?` | [ISelectType](../globals.md#iselecttype)[] &#124; string &#124; undefined |

**Returns:** *[Query](query.md)*

___

###  useKeys

▸ **useKeys**(`value`: string[]): *[Query](query.md)*

*Overrides [BaseQuery](basequery.md).[useKeys](basequery.md#abstract-usekeys)*

Add USE KEYS expression to SELECT clause.

**`method`** 

**`example`** 
```ts
  const query = new Query({}, 'travel-sample');
  const result = query.select([{$field: 'address'}]).useKeys(['airlineR_8093']).build()
  console.log(result)
```
> SELECT address FROM `travel-sample USE KEYS ['airlineR_8093']`

**Parameters:**

Name | Type |
------ | ------ |
`value` | string[] |

**Returns:** *[Query](query.md)*

___

###  usingGSI

▸ **usingGSI**(): *[Query](query.md)*

Create INDEX using General Secondary Index(GSI).

**`method`** 

**`example`** 
```ts
  const result = new Query({}, 'travel-sample').index('CREATE', 'travel_sample_id_test').usingGSI().build();
  console.log(result)
```
> CREATE INDEX `travel_sample_id_test` USING GSI)

**Returns:** *[Query](query.md)*

___

###  where

▸ **where**(`value`: [LogicalWhereExpr](../globals.md#logicalwhereexpr)): *[Query](query.md)*

*Overrides [BaseQuery](basequery.md).[where](basequery.md#abstract-where)*

Add WHERE expression to SELECT clause.

**`method`** 

**`example`** 
```ts
  const expr_where = {$or: [{ address: { $like: '%57-59%' } }, { free_breakfast: true }]};
  const query = new Query({}, 'travel-sample');
  const result = query.select([{$field: 'address'}]).where(expr_where).build()
  console.log(result)
```
> SELECT address FROM `travel-sample WHERE (address LIKE '%57-59%' OR free_breakfast = true)`

**Parameters:**

Name | Type |
------ | ------ |
`value` | [LogicalWhereExpr](../globals.md#logicalwhereexpr) |

**Returns:** *[Query](query.md)*

___

###  with

▸ **with**(`value`: [IIndexWithParams](../interfaces/iindexwithparams.md)): *[Query](query.md)*

Add items to WITH clause in INDEX clause.

**`method`** 

**`example`** 
```ts
  const withExpr = {nodes: ['192.168.1.1:8078'],defer_build: true,num_replica: 2};
  const result = new Query({}, 'travel-sample').index('CREATE', 'travel_sample_id_test').with(withExpr).build();
  console.log(result)
```
> CREATE INDEX `travel_sample_id_test` WITH {'nodes': ['192.168.1.1:8078'],'defer_build': true,'num_replica': 2})

**Parameters:**

Name | Type |
------ | ------ |
`value` | [IIndexWithParams](../interfaces/iindexwithparams.md) |

**Returns:** *[Query](query.md)*
