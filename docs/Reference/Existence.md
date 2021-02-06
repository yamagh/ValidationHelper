# Existence

Verify the existence of the value.

## Parameters

`ExistenceTypeId`
: presence / absence

`Message`
: Custom error message

## Method of verification

### Presence

Verify that the value exists.  
The existing values are:

- The value is not equal to [the default value](https://success.outsystems.com/Documentation/11/Reference/OutSystems_Language/Data/Database_Reference/Default_Values_on_Database) for that data type.
- If the data type of the value is a foreign key, the value exists in the referenced entity.

_Default error message:_

    ${attr} must be present

### Absence

Verify that the value does not exist.  
The non-existent values are:

- The value is equal to [the default value](https://success.outsystems.com/Documentation/11/Reference/OutSystems_Language/Data/Database_Reference/Default_Values_on_Database) for that data type.
- If the data type of the value is a foreign key, the value does not exist in the referenced entity.

_Default error message:_

    ${attr} must be absent
