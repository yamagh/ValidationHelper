# Why need this solution?

## Usual Validation Methods

If you don't yet know the usual validation methods in OutSystems, the following resources may help.

!!! info "Document"
    [Validate the fields of a form - success.outsystems.com](https://success.outsystems.com/Documentation/11/Developing_an_Application/Design_UI/Forms/Validate_the_fields_of_a_form)

!!! info "Video"
    <iframe width="560" height="315" src="https://www.youtube.com/embed/VU3G6ZBeuMI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

The usual way to validate with OutSystems is to implement the logic as follows:

![](../img/why-need-this/1-form-validate-web.png){: loading=lazy }

You can set the properties of the widget to check the required items and the number of characters. However, there are not many validations that can be set in the widget properties. In addition, processing that does not involve a screen may be required, so logic implementation is required anyway.

## Issues

I think there are some issues with this verification method. For example, if you want to use the implemented validation logic in other actions, you will create a common action based on the existing validation logic. The created common action is used for the original action and the newly required action. This means that a small refactoring is needed.

![](../img/why-need-this/2.svg){: loading=lazy }

Also, if you now want to validate in the actions of another module, you may create a common module to keep the dependencies between the modules correct. You need to pay attention to the relationship between the modules. These are a bit of a hassle.

In addition, there is no way to share client-side and server-side validation.

## Why need this solution ?

This solution should help you solve the problems mentioned above. I hope it helps projects that are aware of the same issue.
