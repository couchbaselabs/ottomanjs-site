# Interface: FindOneAndUpdateOption

Find One and Update Options parameter

## Hierarchy

* [IFindOptions](ifindoptions.md)

  ↳ **FindOneAndUpdateOption**

## Properties

### `Optional` consistency

• **consistency**? : *[SearchConsistency](../enums/searchconsistency.md)*

*Inherited from [IFindOptions](ifindoptions.md).[consistency](ifindoptions.md#optional-consistency)*

___

### `Optional` limit

• **limit**? : *undefined | number*

*Inherited from [IFindOptions](ifindoptions.md).[limit](ifindoptions.md#optional-limit)*

___

### `Optional` new

• **new**? : *undefined | false | true*

Default: false
if true, return a document after update otherwise return the document before update.

___

### `Optional` noCollection

• **noCollection**? : *undefined | false | true*

*Inherited from [IFindOptions](ifindoptions.md).[noCollection](ifindoptions.md#optional-nocollection)*

___

### `Optional` populate

• **populate**? : *string | string[]*

*Inherited from [IFindOptions](ifindoptions.md).[populate](ifindoptions.md#optional-populate)*

___

### `Optional` populateMaxDeep

• **populateMaxDeep**? : *undefined | number*

*Inherited from [IFindOptions](ifindoptions.md).[populateMaxDeep](ifindoptions.md#optional-populatemaxdeep)*

___

### `Optional` select

• **select**? : *[ISelectType](../globals.md#iselecttype)[] | string | string[]*

*Inherited from [IFindOptions](ifindoptions.md).[select](ifindoptions.md#optional-select)*

___

### `Optional` skip

• **skip**? : *undefined | number*

*Inherited from [IFindOptions](ifindoptions.md).[skip](ifindoptions.md#optional-skip)*

___

### `Optional` sort

• **sort**? : *Record‹string, [SortType](../globals.md#sorttype)›*

*Inherited from [IFindOptions](ifindoptions.md).[sort](ifindoptions.md#optional-sort)*

___

### `Optional` upsert

• **upsert**? : *undefined | false | true*

Default: false
if true, and no documents found, insert a new document.
