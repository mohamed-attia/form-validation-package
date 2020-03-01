# Form Validation Helper

Form Validation helper for form input validations.
## Installation


```bash
npm install --save form-validation-package
```

## Usage

in HTML file 
```
   <form>
        <label>user name</label>
        <input type="text" name="username" />

        <label>password</label>
        <input type="password" name="password" />

        <button type="submit" id="sendForm">send data</button>
    </form>
```

in app.js file 
```
import {FormValidationModule} from 'form-validation-package';

document.querySelector("#sendForm").addEventListener("click", (e) => {
  e.preventDefault();

  const formValidation = FormValidationModule([
    {
      name: "username",
      rules: [
        { name: "required", value: true, errMsg: "this input is required" },
        { name: "maxlength", value: 10, errMsg: "maxlength error" }
      ]
    },
    {
      name: "password",
      rules: [
        { name: "required", value: true, errMsg: "this input is required" },
        { name: "minlength", value: 5, errMsg: "minlength error" }
      ]
    }
  ]);
  console.log(formValidation)
});
```

PARAMETERS
```
formValidation ([
  {
      name: "Input name that assigned to name property eg: username",
      rules: [
        { name: "required", value: true, errMsg: "this input is required" },
        { name: "maxLength", value: 10, errMsg: "maxlength error" },
        { name: "minLength", value: 3, errMsg: "minlength error" },
        { name: "pattern", value: /\$.js/, errMsg: "Pattern error" },

      ] // array of validation rules
    },
]);

// validation rule object 
{name: 'required | maxLength | minLength | pattern', value: "", errMsg: 'provided error msg'}
```

## License
Form-Validation-Package @2020 dev by: Mohamed Attia

## Keywords
form - formValidation