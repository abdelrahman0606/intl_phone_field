 # International Phone Field Package
<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![All Contributors](https://img.shields.io/badge/all_contributors-8-orange.svg?style=flat-square)](#contributors-)
<!-- ALL-CONTRIBUTORS-BADGE:END -->

[![pub package](https://img.shields.io/pub/v/intl_phone_field.svg)](https://pub.dev/packages/intl_phone_field)

A customised Flutter TextFormField to input international phone number along with country code.

This widget can be used to make customised text field to take phone number input for any country along with an option to choose country code from a dropdown.

## Screenshots

<img src="https://github.com/vanshg395/intl_phone_field/blob/master/1.png?raw=true" height="500px"> <img src="https://github.com/vanshg395/intl_phone_field/blob/master/2.png?raw=true" height="500px"> <img src="https://github.com/vanshg395/intl_phone_field/blob/master/3.png?raw=true" height="500px">

## Installing

To use this package:

```yaml
dependencies:
  intl_phone_field:
    git: https://github.com/Abdo73873/intl_phone_field.git
```

## How to Use

Simply create a `IntlPhoneField` widget, and pass the required params:

```dart
IntlPhoneField(
    decoration: InputDecoration(
        labelText: 'Phone Number',
        border: OutlineInputBorder(
            borderSide: BorderSide(),
        ),
    ),
    initialCountryCode: 'IN',
    onChanged: (phone) {
        print(phone.completeNumber);
    },
)
```



## ✅ Improvements in This Fork

This fork of [`intl_phone_field`](https://pub.dev/packages/intl_phone_field) includes a **fix for the `validator` callback**, which was previously not being triggered when used inside a `Form`.

---

### 🔧 What's fixed?

- The `validator` function now works correctly when `IntlPhoneField` is placed inside a `Form` and `FormState.validate()` is called.
- Error messages are displayed properly below the input field.

---

### 📦 How to use

```dart
IntlPhoneField(
  validator: (phone) {
    if (phone == null || phone.number.isEmpty) {
      return 'Please enter a valid phone number';
    }
    return null;
  },
  // other properties...
)
```


## LICENSE

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
