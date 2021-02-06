# Length

Verify the length of the text.

## Parameters

`LengthTypeId`
:   Specify `min` / `max`

`Number`
:   Threshold used for verification

`Message`
:   Custom error message

## Method of verification

### Min

Verify that the text length is not below the minimum.

_Default error message_:

    ${attr} is too short (minimum is ${count} characters)

### Max

Verify that the text length does not exceed the minimum.

_Default error message:_

    ${attr} is too long (maximum is ${count} characters)
