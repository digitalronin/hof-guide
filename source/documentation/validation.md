# Validation Rules

HOF comes with a number of validators built in as standard.

## Using built-in validators

To add a validator to a field, you add it to a `validate` array on the field configuration.

In most cases it is sufficient to simply add the name of the validator as a string. For example, to make an email field mandatory, and check the email address is correctly formatted:

```js
{
  email: {
    validate: ['required', 'email']
  }
}
```

Some validators require additional arguments, which can be specified as follows:

```js
{
  name: {
    validate: [
      { type: 'maxlength', arguments: 10 }
    ]
  },
  referencenumber: {
    validate: [
      { type: 'regex', arguments: /^[a-z0-9]{9}$/ }
    ]
  }
}
```

Here the validator name is passed as a `type` property, and any arguments as an `arguments` property.

> Note: all validators except `required` will allow an empty input to be valid. If an empty input is not valid then a `required` validator must be applied.

## Validator Types

### required

### regex

### equal

### url

### email

### postcode

### minlength

### maxlength

### exactlength

### alphanum

### numeric

### phonenumber

### ukmobilephone

### date

### before

### after
