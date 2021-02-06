# Numecarity

Verify numericality.

## Parameters

`NumecarityTypeId`
:   Specify `odd` / `even` / `equal_to` / `less_than` / `less_than_or_equal_to` / `greater_than` / `greater_than_or_equal_to`

`Number`
:   Threshold used for verification

`Message`
:   Custom error message


## Method of verification

### Odd

Verify that the value is odd.

_Default error message:_

    ${attr} must be odd

### Even

Verify that the value is even.

_Default error message:_

    ${attr} must be even

### Equal to

Verify that the value is equal to any value.

_Default error message:_

    ${attr} must be equal to ${count}

### Less than

Verify that the value is less than any value.

_Default error message:_

    ${attr} must be less than ${count}

### Less than or equal to

Verify that the value is less than or equal to any value.

_Default error message:_

    ${attr} must be less than or equal to ${count}

### Greater than

Verify that the value exceeds any value.

_Default error message:_

    ${attr} must be greater than ${count}

### Greater than or equal than

Verify that the value is equal to or exceeds any value.

_Default error message:_

    ${attr} must be greater than or equal to ${count}
