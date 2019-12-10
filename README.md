# node-module-example
Demonstration for creating node module and using as dependency


### Install colors module from project root directory

``` javascript
npm install --save ../colors
```

### Verify package.json in project folder

``` javascript
"dependencies": {
  "colors": "file:../colors"
}
```

### Usage

``` javascript
const colors = require('colors');

const _color = colors.getRandomColor();
console.log(`Color name ${_color.name} and HTML code is ${_color.code}`);
```

### Linking a Local Module

If your local module is in heavy development, continually updating packages can be tedious. An alternative would be to link the modules. Linking a module ensures that any updates to the module are immediately reflected in the applications using it.

* Uninstall local module from sampleProject
  * ``` $ npm un colors ```
* Create the global link
  * ``` $ cd ../colors ```
  * ``` $ sudo npm link ```
* Once complete, shell will output
  * ``` Output : /usr/local/lib/node_modules/colors -> /home/USER/colors ```
* Return to project folder and link the package
  * ``` $ cd ../sampleProject ```
  * ``` sudo npm link colors ```
* Shell Output
  * ``` Output : /home/USER/sampleProject/node_modules/colors -> /usr/local/lib/node_modules/colors -> /home/USER/colors ```
  