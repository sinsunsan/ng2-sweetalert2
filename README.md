# ng2-sweetalert2
A service wrapping sweetalert2 for angular 2.

# Install
`npm i -s ng2-sweetalert2`

# Usage

First, make sure you have a CSS loader set up for webpack, like so:
```
{
  test: /\.css/,
  loader: 'style!css'
},
```

If you do not use webpack, comment the line 
require('sweetalert2/dist/sweetalert2.min.css');
in index.js compiled file
And import the css separately from the origin sweetalert2 library


Next, inject `SweetAlertService` into a component:
```js
import { SweetAlertService } from 'ng2-sweetalert2';

@Component({
  // if you import theservice globally in a @ngmodule 
  // this line is optional in the component
  providers: [SweetAlertService]
})
export class MyComponent {

 constructor(
    private sweetAlertService: SweetAlertService
 ) {}
 
 // Example method that use the service
 public onClick() {
    this.sweetAlertService.confirm('Are you sure ? ');
  }

```


# API
See [limonte/sweetalert2](https://github.com/limonte/sweetalert2) for examples.

Function  | Arguments | Description
--------  | --------- | -----------
swal      | any       | Create a generic swal with any arguments.
prompt    | object    | Create a swal that prompts user with a basic text entry field.
confirm   | object    | Create a swal that confirms a user action.
alert     | object    | Create a swal that alerts a user of something that happened.
question  | object    | Wrapper for `alert` that sets type to `question`.
success   | object    | Wrapper for `alert` that sets type to `success`.
error     | object    | Wrapper for `alert` that sets type to `error`.
warn      | object    | Wrapper for `alert` that sets type to `warn`.
info      | object    | Wrapper for `alert` that sets type to `info`.
