## angular course
  * Tutorial https://ultimateangular.teachable.com/courses/enrolled/100820
  * Documentation https://angular.io/docs
  * Site https://angular.io/

## login
  * name = my email address
  * password = same as github password

## keyboard mapping
https://code.visualstudio.com/shortcuts/keyboard-shortcuts-linux.pdf

* toggle side bar Ctrl + B
* Ctrl F2 to Rename Symbol
* to scroll the screen up and down use the Ctrl + scroll button
* to scroll the screen left and right use the Ctrl + scroll button

### clone and change remote

```bash
git clone https://github.com/UltimateAngular/ngrx-store-effects-app.git ngrx-store
git config --list
git remote set-url origin https://github.com/NormLorenz/ngrx-store.git
git push -u origin master
```

### install node-sass locally (not globally)

```bash
npm install node-sass
yarn install
```

### source files

* https://github.com/UltimateAngular/angular-fundamentals-src

### notes

* spread operator creates a brand new object
* 

```javascript
const character = { name: 'Han Solo' };

// below two examples are identical
const updatedCharacter = Object.assign({}, character, { role: 'Captain' });
const updatedCharacter = { ...character, role: 'Captain' };
```
