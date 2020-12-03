# Class: BaseQuery

Basic definition of Query Class

## Hierarchy

* **BaseQuery**

  ↳ [Query](query.md)

## Constructors

### `Protected` constructor

\+ **new BaseQuery**(`_conditions`: [IConditionExpr](../interfaces/iconditionexpr.md), `_collection`: string): *[BaseQuery](basequery.md)*

**Parameters:**

Name | Type |
------ | ------ |
`_conditions` | [IConditionExpr](../interfaces/iconditionexpr.md) |
`_collection` | string |

**Returns:** *[BaseQuery](basequery.md)*

## Properties

### `Protected` _collection

• **_collection**: *string*

___

### `Protected` _conditions

• **_conditions**: *[IConditionExpr](../interfaces/iconditionexpr.md)*

## Methods

### `Abstract` build

▸ **build**(): *string*

**Returns:** *string*

___

### `Abstract` let

▸ **let**(`value`: [[ILetExpr](../interfaces/iletexpr.md)]): *[BaseQuery](basequery.md)*

**Parameters:**

Name | Type |
------ | ------ |
`value` | [[ILetExpr](../interfaces/iletexpr.md)] |

**Returns:** *[BaseQuery](basequery.md)*

___

### `Abstract` limit

▸ **limit**(`value`: number): *[BaseQuery](basequery.md)*

**Parameters:**

Name | Type |
------ | ------ |
`value` | number |

**Returns:** *[BaseQuery](basequery.md)*

___

### `Abstract` offset

▸ **offset**(`value`: number): *[BaseQuery](basequery.md)*

**Parameters:**

Name | Type |
------ | ------ |
`value` | number |

**Returns:** *[BaseQuery](basequery.md)*

___

### `Abstract` orderBy

▸ **orderBy**(`value`: Record‹string, [SortType](../globals.md#sorttype)›): *[BaseQuery](basequery.md)*

**Parameters:**

Name | Type |
------ | ------ |
`value` | Record‹string, [SortType](../globals.md#sorttype)› |

**Returns:** *[BaseQuery](basequery.md)*

___

### `Abstract` select

▸ **select**(`value?`: [ISelectType](../globals.md#iselecttype)[] | string | undefined): *[BaseQuery](basequery.md)*

**Parameters:**

Name | Type |
------ | ------ |
`value?` | [ISelectType](../globals.md#iselecttype)[] &#124; string &#124; undefined |

**Returns:** *[BaseQuery](basequery.md)*

___

### `Abstract` useKeys

▸ **useKeys**(`value`: [string]): *[BaseQuery](basequery.md)*

**Parameters:**

Name | Type |
------ | ------ |
`value` | [string] |

**Returns:** *[BaseQuery](basequery.md)*

___

### `Abstract` where

▸ **where**(`value`: [LogicalWhereExpr](../globals.md#logicalwhereexpr)): *[BaseQuery](basequery.md)*

**Parameters:**

Name | Type |
------ | ------ |
`value` | [LogicalWhereExpr](../globals.md#logicalwhereexpr) |

**Returns:** *[BaseQuery](basequery.md)*
