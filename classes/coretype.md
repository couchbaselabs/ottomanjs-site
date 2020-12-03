# Class: CoreType

**`param`** of field in schema

**`param`** name of type

**`param`** 

**`param`** flag to define if the field is mandatory

**`param`** that will be applied to the field, allowed function, object or string with the name of the custom validator

**`param`** that will define the initial value of the field, allowed and value or function to generate it

**`param`** that will generate the initial value of the field. if the field is String it allows the value 'uuid' or a function, in any other cases only functions. It cannot be used combined with default

## Hierarchy

* [IOttomanType](iottomantype.md)

  ↳ **CoreType**

  ↳ [StringType](stringtype.md)

  ↳ [BooleanType](booleantype.md)

  ↳ [NumberType](numbertype.md)

  ↳ [DateType](datetype.md)

  ↳ [ArrayType](arraytype.md)

  ↳ [EmbedType](embedtype.md)

  ↳ [ReferenceType](referencetype.md)

## Constructors

### `Protected` constructor

\+ **new CoreType**(`name`: string, `typeName`: string, `options?`: [CoreTypeOptions](../interfaces/coretypeoptions.md)): *[CoreType](coretype.md)*

*Overrides [IOttomanType](iottomantype.md).[constructor](iottomantype.md#protected-constructor)*

**Parameters:**

Name | Type |
------ | ------ |
`name` | string |
`typeName` | string |
`options?` | [CoreTypeOptions](../interfaces/coretypeoptions.md) |

**Returns:** *[CoreType](coretype.md)*

## Properties

###  name

• **name**: *string*

*Inherited from [IOttomanType](iottomantype.md).[name](iottomantype.md#name)*

___

### `Optional` options

• **options**? : *[CoreTypeOptions](../interfaces/coretypeoptions.md)*

___

###  typeName

• **typeName**: *string*

*Inherited from [IOttomanType](iottomantype.md).[typeName](iottomantype.md#typename)*

## Accessors

###  auto

• **get auto**(): *string | [AutoFunction](../globals.md#autofunction) | undefined*

**Returns:** *string | [AutoFunction](../globals.md#autofunction) | undefined*

___

###  default

• **get default**(): *unknown*

**Returns:** *unknown*

___

###  required

• **get required**(): *boolean | [RequiredOption](../interfaces/requiredoption.md) | [RequiredFunction](../globals.md#requiredfunction)*

**Returns:** *boolean | [RequiredOption](../interfaces/requiredoption.md) | [RequiredFunction](../globals.md#requiredfunction)*

___

###  validator

• **get validator**(): *[ValidatorOption](../interfaces/validatoroption.md) | [ValidatorFunction](../globals.md#validatorfunction) | string | undefined*

**Returns:** *[ValidatorOption](../interfaces/validatoroption.md) | [ValidatorFunction](../globals.md#validatorfunction) | string | undefined*

## Methods

###  buildDefault

▸ **buildDefault**(): *unknown*

**Returns:** *unknown*

___

###  cast

▸ **cast**(`value`: unknown, `strategy`: [VALIDATION_STRATEGY](../enums/validation_strategy.md)): *unknown*

*Overrides [IOttomanType](iottomantype.md).[cast](iottomantype.md#abstract-cast)*

**Parameters:**

Name | Type |
------ | ------ |
`value` | unknown |
`strategy` | [VALIDATION_STRATEGY](../enums/validation_strategy.md) |

**Returns:** *unknown*

___

###  checkRequired

▸ **checkRequired**(): *string | void*

**Returns:** *string | void*

___

###  checkValidator

▸ **checkValidator**(`value`: unknown): *void*

**Parameters:**

Name | Type |
------ | ------ |
`value` | unknown |

**Returns:** *void*

___

###  isEmpty

▸ **isEmpty**(`value`: unknown): *boolean*

**Parameters:**

Name | Type |
------ | ------ |
`value` | unknown |

**Returns:** *boolean*

___

###  isStrictStrategy

▸ **isStrictStrategy**(`strategy`: [VALIDATION_STRATEGY](../enums/validation_strategy.md)): *boolean*

**Parameters:**

Name | Type |
------ | ------ |
`strategy` | [VALIDATION_STRATEGY](../enums/validation_strategy.md) |

**Returns:** *boolean*
