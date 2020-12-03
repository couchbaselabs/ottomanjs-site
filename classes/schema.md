# Class: Schema

## Hierarchy

* **Schema**

## Constructors

###  constructor

\+ **new Schema**(`obj`: [SchemaDef](../globals.md#schemadef) | [Schema](schema.md), `options?`: [SchemaOptions](../interfaces/schemaoptions.md)): *[Schema](schema.md)*

**`summary`** Creates an instance of Schema

**`name`** Schema

**`example`** 
```ts
 const schema = new Schema({name: String, age: {type: Number, intVal: true, min: 18}});
```

**Parameters:**

Name | Type | Description |
------ | ------ | ------ |
`obj` | [SchemaDef](../globals.md#schemadef) &#124; [Schema](schema.md) | Schema definition |
`options?` | [SchemaOptions](../interfaces/schemaoptions.md) | Settings to build schema |

**Returns:** *[Schema](schema.md)*

Schema

## Properties

###  fields

• **fields**: *[FieldMap](../globals.md#fieldmap)*

___

###  index

• **index**: *[SchemaIndex](../globals.md#schemaindex)*

___

###  methods

• **methods**: *any*

___

###  postHooks

• **postHooks**: *any*

___

###  preHooks

• **preHooks**: *any*

___

###  queries

• **queries**: *[SchemaQuery](../globals.md#schemaquery)*

___

###  statics

• **statics**: *any*

___

###  validationStrategy

• **validationStrategy**: *[VALIDATION_STRATEGY](../enums/validation_strategy.md)*

___

### `Static` validators

▪ **validators**: *[CustomValidations](../globals.md#customvalidations)*

## Methods

###  applyDefaultsToObject

▸ **applyDefaultsToObject**(`obj`: any): *any*

Applies default values defined on schema to an object instance

**`method`** 

**`example`** 
```ts
  const schema = new Schema({ amount: { type: Number, default: 5}});
  const result = schema.applyDefaultsToObject({});
  console.log(result)
```
> { amount: 5 }

**Parameters:**

Name | Type |
------ | ------ |
`obj` | any |

**Returns:** *any*

___

###  cast

▸ **cast**(`object`: any): *any*

Casts a model instance using the definition of the schema

**`method`** 

**`example`** 
```ts
  const schema = new Schema({name: String, age: {type: Number, intVal: true, min: 18}});
  const result = schema.cast({name: 'John Doe', age: '34'});
  console.log(result)
```
> {name: 'John Doe', age: 34}

**Parameters:**

Name | Type |
------ | ------ |
`object` | any |

**Returns:** *any*

___

###  path

▸ **path**(`path`: string): *[IOttomanType](iottomantype.md) | undefined*

Allows access to specify field.

**`example`** 
```ts
  const schema = new Schema({ amount: { type: Number, default: 5}});
  const field = schema.path('amount');
  console.log(field.typeName);
```
> Number

**Parameters:**

Name | Type |
------ | ------ |
`path` | string |

**Returns:** *[IOttomanType](iottomantype.md) | undefined*

___

###  plugin

▸ **plugin**(...`fns`: [PluginConstructor](../globals.md#pluginconstructor)[]): *[Schema](schema.md)*

Allows to apply plugins, to extend schema and model features.

**`example`** 
```ts
  const schema = new Schema({ amount: { type: Number, default: 5}});
  schema.plugin((schema) => console.log(schema.path('amount').typeName));
```
> Number

**Parameters:**

Name | Type |
------ | ------ |
`...fns` | [PluginConstructor](../globals.md#pluginconstructor)[] |

**Returns:** *[Schema](schema.md)*

___

###  post

▸ **post**(`hook`: [HookTypes](../globals.md#hooktypes), `handler`: [HookHandler](../globals.md#hookhandler)): *[Schema](schema.md)*

Allows to register a hook function.
Post hooks are executed after the hooked method.

**`example`** 
```ts
  const schema = new Schema({ amount: { type: Number, default: 5}});
  schema.post(HOOKS.validate, (doc) => console.log(doc));
```

**Parameters:**

Name | Type |
------ | ------ |
`hook` | [HookTypes](../globals.md#hooktypes) |
`handler` | [HookHandler](../globals.md#hookhandler) |

**Returns:** *[Schema](schema.md)*

___

###  pre

▸ **pre**(`hook`: [HookTypes](../globals.md#hooktypes), `handler`: [HookHandler](../globals.md#hookhandler)): *[Schema](schema.md)*

Allows to register a hook method.
Pre hooks are executed before the hooked method.

**`example`** 
```ts
  const schema = new Schema({ amount: { type: Number, default: 5}});
  schema.pre(HOOKS.validate, (doc) => console.log(doc));
```

**Parameters:**

Name | Type |
------ | ------ |
`hook` | [HookTypes](../globals.md#hooktypes) |
`handler` | [HookHandler](../globals.md#hookhandler) |

**Returns:** *[Schema](schema.md)*

## Object literals

### `Static` Types

### ▪ **Types**: *object*

###  Array

• **Array**: *arrayTypeFactory* = arrayTypeFactory

###  Boolean

• **Boolean**: *booleanTypeFactory* = booleanTypeFactory

###  Date

• **Date**: *dateTypeFactory* = dateTypeFactory

###  Embed

• **Embed**: *embedTypeFactory* = embedTypeFactory

###  Number

• **Number**: *numberTypeFactory* = numberTypeFactory

###  Reference

• **Reference**: *referenceTypeFactory* = referenceTypeFactory

###  String

• **String**: *stringTypeFactory* = stringTypeFactory
