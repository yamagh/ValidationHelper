# Uniqueness

Verify that the element is unique among the attributes of the specified entity.

## Parameters

`Scope` (Option)
: Other attributes used to determine uniqueness constraints. When specifying multiple attributes, specify a space-separated list. If not specified, it validates that it is unique among all records of the corresponding attribute. It is not case sensitive.

`Message` (Option)
:   Custom error message

_Default error message:_

    ${attr} has already been taken.

!!! info "Remarks"
    This validation rule does not create a unique constraint on the database. Therefore, it is possible that two database connections happen to create two records with the same value in an attribute that should be unique. To avoid this, you need to create a unique index on that attribute of the database.
