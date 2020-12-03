# Class: DateType

**`inheritdoc`** 

**`param`** date value that will be accepted

**`param`** date value that will be accepted

## Hierarchy

  ↳ [CoreType](coretype.md)

  ↳ **DateType**

## Constructors

###  constructor

\+ **new DateType**(`name`: string, `options?`: [DateTypeOptions](../interfaces/datetypeoptions.md) & [CoreTypeOptions](../interfaces/coretypeoptions.md)): *[DateType](datetype.md)*

*Overrides [CoreType](coretype.md).[constructor](coretype.md#protected-constructor)*

**Parameters:**

Name | Type |
------ | ------ |
`name` | string |
`options?` | [DateTypeOptions](../interfaces/datetypeoptions.md) & [CoreTypeOptions](../interfaces/coretypeoptions.md) |

**Returns:** *[DateType](datetype.md)*

## Properties

###  name

• **name**: *string*

*Inherited from [IOttomanType](iottomantype.md).[name](iottomantype.md#name)*

___

### `Optional` options

• **options**? : *[CoreTypeOptions](../interfaces/coretypeoptions.md)*

*Inherited from [CoreType](coretype.md).[options](coretype.md#optional-options)*

___

###  typeName

• **typeName**: *string*

*Inherited from [IOttomanType](iottomantype.md).[typeName](iottomantype.md#typename)*

## Accessors

###  auto

• **get auto**(): *string | [AutoFunction](../globals.md#autofunction) | undefined*

*Inherited from [CoreType](coretype.md).[auto](coretype.md#auto)*

**Returns:** *string | [AutoFunction](../globals.md#autofunction) | undefined*

___

###  default

• **get default**(): *unknown*

*Inherited from [CoreType](coretype.md).[default](coretype.md#default)*

**Returns:** *unknown*

___

###  max

• **get max**(): *Date | [DateOption](../interfaces/dateoption.md) | [DateFunction](../globals.md#datefunction) | undefined*

**Returns:** *Date | [DateOption](../interfaces/dateoption.md) | [DateFunction](../globals.md#datefunction) | undefined*

___

###  min

• **get min**(): *Date | [DateOption](../interfaces/dateoption.md) | [DateFunction](../globals.md#datefunction) | undefined*

**Returns:** *Date | [DateOption](../interfaces/dateoption.md) | [DateFunction](../globals.md#datefunction) | undefined*

___

###  required

• **get required**(): *boolean | [RequiredOption](../interfaces/requiredoption.md) | [RequiredFunction](../globals.md#requiredfunction)*

*Inherited from [CoreType](coretype.md).[required](coretype.md#required)*

**Returns:** *boolean | [RequiredOption](../interfaces/requiredoption.md) | [RequiredFunction](../globals.md#requiredfunction)*

___

###  validator

• **get validator**(): *[ValidatorOption](../interfaces/validatoroption.md) | [ValidatorFunction](../globals.md#validatorfunction) | string | undefined*

*Inherited from [CoreType](coretype.md).[validator](coretype.md#validator)*

**Returns:** *[ValidatorOption](../interfaces/validatoroption.md) | [ValidatorFunction](../globals.md#validatorfunction) | string | undefined*

## Methods

###  buildDefault

▸ **buildDefault**(): *Date*

*Overrides [CoreType](coretype.md).[buildDefault](coretype.md#builddefault)*

**Returns:** *Date*

___

###  cast

▸ **cast**(`value`: unknown, `strategy`: any): *unknown*

*Overrides [CoreType](coretype.md).[cast](coretype.md#cast)*

**Parameters:**

Name | Type |
------ | ------ |
`value` | unknown |
`strategy` | any |

**Returns:** *unknown*

___

###  checkRequired

▸ **checkRequired**(): *string | void*

*Inherited from [CoreType](coretype.md).[checkRequired](coretype.md#checkrequired)*

**Returns:** *string | void*

___

###  checkValidator

▸ **checkValidator**(`value`: unknown): *void*

*Inherited from [CoreType](coretype.md).[checkValidator](coretype.md#checkvalidator)*

**Parameters:**

Name | Type |
------ | ------ |
`value` | unknown |

**Returns:** *void*

___

###  isEmpty

▸ **isEmpty**(`value`: unknown): *boolean*

*Inherited from [CoreType](coretype.md).[isEmpty](coretype.md#isempty)*

**Parameters:**

Name | Type |
------ | ------ |
`value` | unknown |

**Returns:** *boolean*

___

###  isStrictStrategy

▸ **isStrictStrategy**(`strategy`: [VALIDATION_STRATEGY](../enums/validation_strategy.md)): *boolean*

*Inherited from [CoreType](coretype.md).[isStrictStrategy](coretype.md#isstrictstrategy)*

**Parameters:**

Name | Type |
------ | ------ |
`strategy` | [VALIDATION_STRATEGY](../enums/validation_strategy.md) |

**Returns:** *boolean*
