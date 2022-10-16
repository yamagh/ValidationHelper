## Server Actions

### ![](/icon/action-server-32x32.png) IsValidEntity

Validate entity based on Validation Rules.

#### Parameters

![](/docs/img/Reference/InputParameter-1.png) Object `EntityObject` (Mandatory)
: Specify the Entity object to be validated. To specify an Entity object, use the `ToObject` function.
Example: `ToObject(GetFooById.List.Current.Foo)`

![](/docs/img/Reference/InputParameter-1.png) Boolean `IsOccurException` (Mandatory)
: If True, an exception is raised if the validation does not pass.

![](/docs/img/Reference/InputParameter-1.png) Structure `ErrorFormat`
: Format of the error message if `IsOccurException` is True and the validation did not pass.

  **Text `Prefix`**

    - Prefix to be given to error messages if they do not pass validation.
    - Default Value: `"${ErrorCount} Validation Error(s).<ul>"`
    - Avalidable Placeholders:
      - `${ErrorCount}`: Number of total errors.
  
  **Text `Detail`**

    - If the validation does not pass, the format of the error message details.
    - Default Value: `"<li>${ErrorMessage}</li>"`
    - Avalidable Placeholders:
      - `${ErrorMessage}`
        - Details for one validation error.
        - ex) "FooBar is too short (minimum is 10 characters)"
      - `${AttrName}`
        - Name of the attribute that caused the validation error
        - ex) "FirstName"
  
  **Text `DetailSeparator`**

    - Separator for each error detail.
    - Default Value: `""`
  
  **Text `Suffix`**

    - Suffix error messages.
    - Default Value: `"</ul>"`

![](/docs/img/Reference/OutputParameter-0.png) Boolean `IsValid`
: True if validation is passed.

![](/docs/img/Reference/OutputParameter-0.png) List `ErrorList (AttrName, Message)`
: If the validation did not pass, a list of details of the error. With an error message for each attribute.

### ![](/icon/action-server-32x32.png) HasError

Returns the error message for the specified attribute in ErrorList (`IsValidEntity` Action's output).

#### Parameters

![](/docs/img/Reference/InputParameter-1.png) Structure `ErrorList (AttrName, Message)` (Mandatory)
: `IsValidEntity` Action's output.

![](/docs/img/Reference/InputParameter-1.png) Structure `AttrName` (Mandatory)
: Attribute name to be retrieved from ErrorList. Ignore case.

![](/docs/img/Reference/OutputParameter-0.png) Structure `Out (IsValid, Message)`
: `IsValid` is False if `AttrName` is in `ErrorList`.

## Client Actions

### ![](/icon/action-client-32x32.png) IsValidEntity

Validate entity based on Validation Rules.

#### Parameters

![](/docs/img/Reference/InputParameter-1.png) Object `EntityObject` (Mandatory)
: See `IsValidEntity` in Server Action

![](/docs/img/Reference/InputParameter-1.png) Boolean `IsOccurException` (Mandatory)
: See `IsValidEntity` in Server Action

![](/docs/img/Reference/InputParameter-1.png) Structure `ErrorFormat`
: See `IsValidEntity` in Server Action

![](/docs/img/Reference/InputParameter-1.png) Integer `CacheInMinutes`
: Time to cache the validation rules. If the cache becomes invalid, the validation rule is re-fetched from the server.

  - Default Value: 1440

![](/docs/img/Reference/OutputParameter-0.png) Boolean `IsValid`
: See `IsValidEntity` in Server Action

![](/docs/img/Reference/OutputParameter-0.png) List `ErrorList (AttrName, Message)`
: See `IsValidEntity` in Server Action

### ![](/icon/action-client-32x32.png) HasError

Returns the error message for the specified attribute in ErrorList (`IsValidEntity` Action's output).

#### Parameters

![](/docs/img/Reference/InputParameter-1.png) Structure `ErrorList (AttrName, Message)` (Mandatory)
: See `HasError` in Server Action

![](/docs/img/Reference/InputParameter-1.png) Text `AttrName` (Mandatory)
: Attribute name to be retrieved from ErrorList. Ignore case. If you do not want to hardcode attribute names, you can use the `NameOf` action.

![](/docs/img/Reference/OutputParameter-0.png) Structure `Out (IsValid, Message)`
: See `HasError` in Server Action

### ![](/icon/action-client-32x32.png) NameOf

Get the name of the object.
Note: This action is experimental

#### Parameters

![](/docs/img/Reference/InputParameter-1.png) Object `Object` (Mandatory)
: Specify the object for which you want to get a name.

    ```js
    Examples:
    ToObject(GetFooById.List.Current.Foo.Bar)
    # Output = bar
    
    ToObject(GetFooById.List.Current.Foo)
    # Output = foo
    
    ToObject(GetFooById.List.Current)
    # Output = Current
    
    ToObject(GetFooById.List[1])
    # Output = List[1]
    
    ToObject(Foo.Bar)
    # Output = bar
    
    ToObject(Foo)
    # Output = foo
    ```

![](/docs/img/Reference/OutputParameter-0.png) Text `Name`
: Object Name

### ![](/docs/img/Reference/ClientAction16.png) Message

Wrapper for [FeedbackMessage](https://success.outsystems.com/Documentation/11/Reference/OutSystems_APIs/JavaScript_API/FeedbackMessage?_gl=1*136xofe*_ga*MTQwNDI0MjEwNC4xNjY0MDcwODQz*_ga_ZD4DTMHWR2*MTY2NTQxMjUzOC4zOS4xLjE2NjU0MTI1NDAuNTguMC4w) API in OutSystems' standard JavaScript API. The error message returned by default by the `IsValidEntity` action contains HTML `<br>` and `<ul>` tags, but you must use this `Message` action with the input parameter `encodeHTML` set to False in order to correctly display this error message in your feedback message.

#### Parameters

![](/docs/img/Reference/InputParameter-1.png) Text `message` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `messageType` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `encodeHTML` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `extraCssClasses` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `closeOnClick` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `onClick` (Mandatory)

### ![](/docs/img/Reference/MessageError16.png) Message_Error

Shortcut for error messages.

#### Parameters

![](/docs/img/Reference/InputParameter-1.png) Text `message` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `encodeHTML` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `extraCssClasses` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `closeOnClick` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `onClick` (Mandatory)

### ![](/docs/img/Reference/MessageInfo16.png) Message_Info

Shortcut for info messages.

#### Parameters

![](/docs/img/Reference/InputParameter-1.png) Text `message` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `encodeHTML` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `extraCssClasses` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `closeOnClick` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `onClick` (Mandatory)

### ![](/docs/img/Reference/MessageSuccess16.png) Message_Success

Shortcut for success messages.

#### Parameters

![](/docs/img/Reference/InputParameter-1.png) Text `message` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `encodeHTML` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `extraCssClasses` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `closeOnClick` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `onClick` (Mandatory)

### ![](/docs/img/Reference/MessageWarning16.png) Message_Warning

Shortcut for warning messages.

#### Parameters

![](/docs/img/Reference/InputParameter-1.png) Text `message` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `encodeHTML` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `extraCssClasses` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `closeOnClick` (Mandatory)
![](/docs/img/Reference/InputParameter-1.png) Text `onClick` (Mandatory)

## Validation Types

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
