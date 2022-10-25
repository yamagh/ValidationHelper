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

## Examples

##### Example #1

The validation will pass under the following conditions.
There is no record in Fig. 1 that matches "Year" and "Num".

###### Fig.1 - Data at the time of validation

|  Id | Year | Num | Content | IsActive |
| --: | ---: | --: | ------- | -------- |
|   1 | 2021 |   1 | Foo     | True     |
|   2 | 2022 |   1 | Bar     | True     |

###### Fig.2 - Target record to be verified

|  Id | Year | Num | Content | IsActive |
| --: | ---: | --: | ------- | -------- |
|   3 | 2022 |   2 | Baz     | True     |

###### Uniqueness rule for "Num"

- `Scope` = `"Year"`

##### Example #2

The validation will not pass under the following conditions.
There is a record in Fig. 3 whose "Year" and "Num" match.

###### Fig.3 - Data at the time of validation

|  Id | Year | Num | Content | IsActive |
| --: | ---: | --: | ------- | -------- |
|   1 | 2021 |   1 | Foo     | True     |
|   2 | 2022 |   1 | Bar     | True     |

###### Fig.4 - Target record to be verified

|  Id | Year | Num | Content | IsActive |
| --: | ---: | --: | ------- | -------- |
|   3 | 2022 |   1 | Baz     | True     |

###### Uniqueness rule for "Num"

- `Scope` = `"Year"`

##### Example #3

The validation will pass under the following conditions.
There is no record in Fig. 5 that matches "Year", "IsActive", and "Num".

###### Fig.5 - Data at the time of validation

|  Id | Year | Num | Content | IsActive |
| --: | ---: | --: | ------- | -------- |
|   1 | 2021 |   1 | Foo     | True     |
|   2 | 2022 |   1 | Bar     | False     |

###### Fig.6 - Target record to be verified

|  Id | Year | Num | Content | IsActive |
| --: | ---: | --: | ------- | -------- |
|   3 | 2022 |   1 | Baz     | True     |

###### Uniqueness rule for "Num"

- `Scope` = `"Year IsActive"`

##### Example #4

The validation will pass under the following conditions
Record with the same Id (primary key) are ignored.

###### Fig.7 - Data at the time of validation

|  Id | Year | Num | Content | IsActive |
| --: | ---: | --: | ------- | -------- |
|   1 | 2021 |   1 | Foo     | True     |
|   2 | 2022 |   1 | Bar     | True     |

###### Fig.8 - Target record to be verified

|  Id | Year | Num | Content | IsActive |
| --: | ---: | --: | ------- | -------- |
|   2 | 2022 |   1 | Qux     | True     |

###### Uniqueness rule for "Num"

- `Scope` = `"Year"`
