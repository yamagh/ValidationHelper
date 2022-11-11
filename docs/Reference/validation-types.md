You can define validation rules from the following types of validation methods:

- **Element:** Inclusion, Exclusion
- **Existence:** Presence, Absence
- **Format:** With, Without
- **Length:** Min, Max
- **Numecarity:** Odd, Even, Equal to, Less than, Less thaan or equal to, Greater than, Greater than or equal to
- **Uniqueness**

You can define all types of validation for attributes of all data types. When validating, the data is implicitly transformed and then validated, depending on the type of validation.

!!! Note
    [This component](https://www.outsystems.com/forge/component-overview/5391/objecttorecordlist-using-c-reflection) is used for the implicit conversion. See this component if you want to know more about the conversion. We recommend that you use a validation method that matches your data type to avoid unexpected implicit conversion results.
