# Element

Verify the elements contained in the text.

## Parameters

`ElementTypeId`
: Specify `inclustion` / `exclusion`

`List`
:   List of words used for verification

`Delimiters`
:   Delimiter used in the `List`

`Message`
:   Custom error message

## Method of verification

### Inclusion

Verify that the text contains any words.  
You can specify multiple words to confirm that they are included, separated by spaces.

_Default error message:_

    ${attr} is not included in the list

### Exclusion

Verify that the text does not contain any words.  
You can specify multiple words to confirm that they are included, separated by spaces.

_Default error message:_

    ${attr} is reserved