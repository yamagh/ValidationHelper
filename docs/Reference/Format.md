# Format

Verify text format with regular expressions.  
Use OutSystems' [Text API/Regex_Search](https://success.outsystems.com/Documentation/11/Reference/OutSystems_APIs/Text_API#Regex_Search) for regular expression matching.

## Parameters

`FormatTypeId`
:   Specify `with` / `without`g

`Pattern`
:   Regular expression pattern used in validation

`IgnoreCase`
:   IgnoreCase option to use with regular expressions

`MultiLine`
:   Multiline option to use with regular expressions

`SingleLine`
:   SingleLine option to use with regular expressions

`Message`
:   Custom error message

## Method of verification

### With

Verify that it matches the text format.

_Default error message:_

    ${attr} is invalid.

### Without

Verify that it does not match the text format.

_Default error message:_

    ${attr} is invalid.
