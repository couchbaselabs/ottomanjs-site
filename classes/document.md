# Class: Document ‹**T**›

Document class represent a database document
and provide some useful methods to work with.

**`example`** 
```javascript
import { connect, model } from "ottoman";
connect("couchbase://localhost/travel-sample@admin:password");

// Create an `User` model
const User = model('User', { name: String });

// Create a document from the `User` Model
const jane = new User({name: "Jane Doe"})
```

## Type parameters

▪ **T**

## Hierarchy

* **Document**

  ↳ [Model](model.md)

## Methods

###  _applyData

▸ **_applyData**(`data`: any): *void*

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

Returns id key

**Returns:** *string*

___

###  _populate

▸ **_populate**(`fieldsName`: string | string[], `deep`: number): *Promise‹this›*

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

Returns a Javascript object to be serialized to JSON

**Returns:** *this*

___

###  toObject

▸ **toObject**(): *this*

Returns a Javascript object with data

**Returns:** *this*
