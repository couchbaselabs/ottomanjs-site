# Interface: IConditionExpr

List of params to build a SELECT clause

## Hierarchy

* **IConditionExpr**

## Properties

### `Optional` groupBy

• **groupBy**? : *[IGroupBy](igroupby.md)[]*

___

### `Optional` having

• **having**? : *[LogicalWhereExpr](../globals.md#logicalwhereexpr)*

___

### `Optional` let

• **let**? : *[ILetExpr](iletexpr.md)[]*

___

### `Optional` letting

• **letting**? : *[ILetExpr](iletexpr.md)[]*

___

### `Optional` limit

• **limit**? : *undefined | number*

___

### `Optional` offset

• **offset**? : *undefined | number*

___

### `Optional` orderBy

• **orderBy**? : *Record‹string, [SortType](../globals.md#sorttype)›*

___

### `Optional` select

• **select**? : *[ISelectType](../globals.md#iselecttype)[] | string*

___

### `Optional` use

• **use**? : *string[]*

___

### `Optional` where

• **where**? : *[LogicalWhereExpr](../globals.md#logicalwhereexpr)*
