# Form Validation Helper

Form Validation helper for form input validations.
## Installation


```bash
npm install -------
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
import {FormValidationModule} from './formValidationModule';

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



## License
Mohamed Attia
