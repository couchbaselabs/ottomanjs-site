# Class: Model ‹**T**›

Constructor to build a model instance based on a schema and other options.
Provides methods to handle documents of the current collection in the database

**`example`** 
```javascript
import { connect, model } from "ottoman";
connect("couchbase://localhost/travel-sample@admin:password");

// Create an `User` model
const User = model('User', { name: String });
```

## Type parameters

▪ **T**

## Hierarchy

* [Document](document.md)‹T›

  ↳ **Model**

## Constructors

###  constructor

\+ **new Model**(`data`: any): *[Model](model.md)*

Creates a document from this model.
Implements schema validations, defaults, methods, static and hooks

**Parameters:**

Name | Type |
------ | ------ |
`data` | any |

**Returns:** *[Model](model.md)*

## Methods

###  _applyData

▸ **_applyData**(`data`: any): *void*

*Inherited from [Document](document.md).[_applyData](document.md#_applydata)*

Allows to easily apply data from an object to current document.

**`example`** 
```javascript
const user = new User({name: "John Doe"});

user._applyData({name: "Jane Doe"});
console.log(user) // {name: "Jane Doe"}
```

**Parameters:**

Name | Type |
------ | ------ |
`data` | any |

**Returns:** *void*

___

###  _depopulate

▸ **_depopulate**(`fieldsName`: string | string[]): *this*

*Inherited from [Document](document.md).[_depopulate](document.md#_depopulate)*

Reverts population. Switches back document reference

**`example`** 
To get in context about the Card and Issue Models [see the populate example.](/classes/document.html#populate)
```javascript
const card = await Card.findById(cardId);
console.log(card.issues); // ['issueId']

await card._populate('issues')
console.log(card.issues); // [{id: 'issueId', title: 'Broken card'}]

card._depopulate('issues')
console.log(card.issues); // ['issueId']
```

**Parameters:**

Name | Type |
------ | ------ |
`fieldsName` | string &#124; string[] |

**Returns:** *this*

___

###  _getId

▸ **_getId**(): *string*

*Inherited from [Document](document.md).[_getId](document.md#_getid)*

Returns id value, useful when working with dynamic ID_KEY

**`example`** 
```javascript
  console.log(user._getId()); // 'userId'
  console.log(user.id); // 'userId'
```

**Returns:** *string*

___

###  _getIdField

▸ **_getIdField**(): *string*

*Inherited from [Document](document.md).[_getIdField](document.md#_getidfield)*

Returns id key

**Returns:** *string*

___

###  _populate

▸ **_populate**(`fieldsName`: string | string[], `deep`: number): *Promise‹this›*

*Inherited from [Document](document.md).[_populate](document.md#_populate)*

Allows to load document references

**`example`** 
Getting context to explain populate.
```javascript
const CardSchema = new Schema({
  number: String,
  zipCode: String,
  issues: [{ type: IssueSchema, ref: 'Issue' }],
});

const IssueSchema = new Schema({
  title: String,
  description: String,
});

const Card = model('Card', CardSchema);
const Issue = model('Issue', CardSchema);

const issue = await Issue.create({ title: 'Broken card' });

const card = await Card.create({
  cardNumber: '4242 4242 4242 4242',
  zipCode: '42424',
  issues: [issue.id],
});
```

Now we will see how the _populate methods works.
```javascript
const card = await Card.findById(cardId);
console.log(card.issues); // ['issueId']

await card.populate('issues')
console.log(card.issues); // [{id: 'issueId', title: 'Broken card'}]
```

**Parameters:**

Name | Type | Default |
------ | ------ | ------ |
`fieldsName` | string &#124; string[] | - |
`deep` | number | DEFAULT_POPULATE_MAX_DEEP |

**Returns:** *Promise‹this›*

___

###  _populated

▸ **_populated**(`fieldName`: string): *boolean*

*Inherited from [Document](document.md).[_populated](document.md#_populated)*

Allows to know if a document field is populated

**`example`** 
To get in context about the Card and Issue Models [see the populate example.](/classes/document.html#populate)
```javascript
const card = await Card.findById(cardId);
console.log(card.issues); // ['issueId']
console.log(card._populated('issues')); // false

await card._populate('issues')
console.log(card.issues); // [{id: 'issueId', title: 'Broken card'}]
console.log(card._populated('issues')); // true
```

**Parameters:**

Name | Type |
------ | ------ |
`fieldName` | string |

**Returns:** *boolean*

___

###  _validate

▸ **_validate**(): *any*

*Inherited from [Document](document.md).[_validate](document.md#_validate)*

Runs schema validations over current document

**`example`** 
```javascript
const user = new User({name: "John Doe"});

try {
  await user._validate()
} catch(errors) {
  console.log(errors)
}
```

**Returns:** *any*

___

###  remove

▸ **remove**(`options`: object): *Promise‹any›*

*Inherited from [Document](document.md).[remove](document.md#remove)*

Removes the document from database

**`example`** 
```javascript
const user = User.findById('userId')

await user.remove();
```

**Parameters:**

Name | Type | Default |
------ | ------ | ------ |
`options` | object | {} |

**Returns:** *Promise‹any›*

___

###  save

▸ **save**(): *Promise‹this›*

*Inherited from [Document](document.md).[save](document.md#save)*

Saves or Updates the document

**`example`** 
```javascript
const user = new User({name: "John Doe"}); //user document created, it's not saved yet

await user.save(); // user saved into the DB
```

**Returns:** *Promise‹this›*

___

###  toJSON

▸ **toJSON**(): *this*

*Inherited from [Document](document.md).[toJSON](document.md#tojson)*

Returns a Javascript object to be serialized to JSON

**Returns:** *this*

___

###  toObject

▸ **toObject**(): *this*

*Inherited from [Document](document.md).[toObject](document.md#toobject)*

Returns a Javascript object with data

**Returns:** *this*

___

### `Static` count

▸ **count**(`filter`: [LogicalWhereExpr](../globals.md#logicalwhereexpr), `options`: [CountOptions](../globals.md#countoptions)): *Promise‹any›*

Returns the number of documents that match the query

**`example`** 
```javascript
User.count({name: {$like: "%Jane%"}})
```

**Parameters:**

Name | Type | Default |
------ | ------ | ------ |
`filter` | [LogicalWhereExpr](../globals.md#logicalwhereexpr) | {} |
`options` | [CountOptions](../globals.md#countoptions) | {} |

**Returns:** *Promise‹any›*

___

### `Static` create

▸ **create**(`data`: Record‹string, any›): *Promise‹any›*

Allows to create a new document

**`example`** 
```javascript
const user = await User.create({name: "John Doe"});
```

**Parameters:**

Name | Type |
------ | ------ |
`data` | Record‹string, any› |

**Returns:** *Promise‹any›*

___

### `Static` find

▸ **find**(`filter`: [LogicalWhereExpr](../globals.md#logicalwhereexpr), `options`: [FindOptions](findoptions.md)): *Promise‹any›*

Finds documents.

**`example`** 
```javascript
User.find({name: "Jane"})
// will return a list of all users with the name "Jane"

User.find({name: "Jane"}, {limit: 10})
// will return a list of all users with the name "Jane" and limited to 10 items

```

```javascript
const filter = {
$or: [{ price: { $gt: 'amount_val', $isNotNull: true } }, { auto: { $gt: 10 } }, { amount: 10 }],
$and: [
  { price2: { $gt: 1.99, $isNotNull: true } },
  { $or: [{ price3: { $gt: 1.99, $isNotNull: true } }, { id: '20' }] },
 ],
};
User.find(filter)
// Returns a list of the elements that match the applied filters.
```

**Parameters:**

Name | Type | Default |
------ | ------ | ------ |
`filter` | [LogicalWhereExpr](../globals.md#logicalwhereexpr) | {} |
`options` | [FindOptions](findoptions.md) | {} |

**Returns:** *Promise‹any›*

___

### `Static` findById

▸ **findById**(`id`: string, `options`: [FindByIdOptions](findbyidoptions.md)): *Promise‹any›*

Allows to retrieve a document by id

**`example`** 
```javascript
User.findById('userId')
// will return the user document with the current id.

User.findById('userId', {select: 'name, cards', populate: 'cards'})
// will return the user document with the current id only with the fields name and cards populated
```

**Parameters:**

Name | Type | Default |
------ | ------ | ------ |
`id` | string | - |
`options` | [FindByIdOptions](findbyidoptions.md) | {} |

**Returns:** *Promise‹any›*

___

### `Static` findOne

▸ **findOne**(`filter`: [LogicalWhereExpr](../globals.md#logicalwhereexpr), `options`: object): *Promise‹any›*

Finds a document.

**`example`** 
```javascript
User.findOne({name: "Jane"})
// will return a document with a User with the name "Jane" or null in case of not finding it
```

**Parameters:**

▪`Default value`  **filter**: *[LogicalWhereExpr](../globals.md#logicalwhereexpr)*= {}

▪`Default value`  **options**: *object*= {}

Name | Type |
------ | ------ |
`sort?` | Record‹string, [SortType](../globals.md#sorttype)› |

**Returns:** *Promise‹any›*

___

### `Static` fromData

▸ **fromData**(`data`: any): *[Model](model.md)‹any›*

Creates a [document](/classes/document) from the given data
Result will be the same that -> new Model(data)

**`example`** 
```javascript
const user = User.fromData({name: "John Doe"});
// we create a `user` document, but it isn't saved yet.

await user.save();
// Now user was persisted to DB
```

**Parameters:**

Name | Type |
------ | ------ |
`data` | any |

**Returns:** *[Model](model.md)‹any›*

___

### `Static` removeById

▸ **removeById**(`id`: string): *Promise‹any›*

Allows to remove a document

**`example`** 
```javascript
const result = await User.removeById('userId');
```

**Parameters:**

Name | Type |
------ | ------ |
`id` | string |

**Returns:** *Promise‹any›*

___

### `Static` replace

▸ **replace**(`data`: any, `id?`: undefined | string): *Promise‹any›*

Allows to replace a document

**`example`** 
```javascript
const user = await User.replace({name: "John Doe"}, 'userId');
```

**Parameters:**

Name | Type |
------ | ------ |
`data` | any |
`id?` | undefined &#124; string |

**Returns:** *Promise‹any›*

___

### `Static` update

▸ **update**(`data`: any, `id?`: undefined | string): *Promise‹any›*

Allows to update a document

**`example`** 
```javascript
const user = await User.update({name: "John Doe"}, 'userId');
```

**Parameters:**

Name | Type |
------ | ------ |
`data` | any |
`id?` | undefined &#124; string |

**Returns:** *Promise‹any›*
