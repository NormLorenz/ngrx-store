## angular course
  * Tutorial https://ultimateangular.teachable.com/courses/enrolled/100820
  * Documentation https://angular.io/docs
  * Site https://angular.io/

## login
  * name = my email address
  * password = same as github password

## keyboard mapping
https://code.visualstudio.com/shortcuts/keyboard-shortcuts-linux.pdf

* Ctrl + B toggle side bar
* Ctrl + F2 to rename symbol
* Ctrl + scroll to scroll the screen up and down
* Shift + scroll to scroll the screen left and right
* F12 goto definition
* Alt + Up or Down move the line up or down

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

* https://github.com/UltimateAngular/ngrx-store-effects-app/branches/stale

### notes

* spread operator creates a brand new object
* change detection strategy onPush technology - detects compares the references instead of the object themselves
* eagerly or lazily loaded modules

* containers components
  * aware of store
  * despatches actions
  * reads data from the store

* presentational components
  * not aware of store
  * invokes callbacks via @Output
  * read data from @Inputs

* the store keeps
  * router state
  * entity state

```javascript
const character = { name: 'Han Solo' };

// below two examples are identical
const updatedCharacter = Object.assign({}, character, { role: 'Captain' });
const updatedCharacter = { ...character, role: 'Captain' };
```
