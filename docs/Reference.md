# Reference

## Validation Types

You can define five types of verification methods:

1. **Length** : Definition of data string length
2. **Element** : Definition of the elements contained in the data
3. **Numecarity** : Definition of the numerical value of data
4. **Presence** : Definition of the existence of data
5. **Format** : Definition of data format

All types of validation can be defined for data of all data types. When validating, the data is implicitly transformed and then validated, depending on the type of validation.

### 1. Length

The string length of the data can be verified in the following ways.

- **Min** : Minimum string length allowed
- **Max** : Maximum string length allowed

### 2. Element

Elements of the data can be validated in the following ways.

- **Inclusion** : Elements to be included in the data
- **Exclusion** : Elements that should not be included in the data

### 3. Numecarity

- **Odd**
- **Even**
- **Equal**
- **Less than**
- **Less or equal than**
- **Greater than**
- **Greater or equal than**

### 4. Presence

The following points define whether or not the data exists.

- **Absent** : Must be equal to [the default value](https://success.outsystems.com/Documentation/11/Reference/OutSystems_Language/Data/Database_Reference/Default_Values_on_Database) for each data type. Or, if the data is a foreign key, it must not be related.
- **Presence** : Opposite for "Absent"

### 5. Format

Whether it matches the format specified by the regular expression.

- **with** : Match the format specified by the regular expression
- **without** : Does not match the format specified by the regular expression
