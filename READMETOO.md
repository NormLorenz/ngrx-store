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
* looks like ngrx store replaces the services we had before
* append a '$' to indicate an observable
* async pipe
* effects
* entities - think of ngrx/store as just a client database (convert action.payload which is an array of object to entities where the key of the object will equal the id of the object)
* explore why todd uses an index.ts in each folder
* ngrx/store bind router state (ngrx/router store) to application state as a single source of truth
* its ok to have multiple store folders
* import in a logical way higher level first

```javascript

  // observables
[pizza]='pizza$ | async'

constructor(private store: Store<fromStore.ProductState>) {}

ngOnInit() {
  this.pizza$ = this.store: Store<fromStore.getSelectedPizza);
}

```

```javascript

// get selected pizza
export const getSelected Pizza = createSelector(
  getPizzasEntities,
  fromRoot.getRouterState,
  (entities, router): Pizza => {
    return router.state && entities[router.state.params.pizzaId];
  }
);

```

```javascript

// ES6 destructuring interesting note: the import statement has the {} destructuring ES6 syntax statement too whereas when we use import * as fromRouter from '@ngrx/router-store' we get everything.

const { url } = routerState;

// import only the destructured arguments
import { createFeatureSelector, ActionReducerMap } from '@ngrx/store';

// whereas this imports everything
import * as fromRouter from '@ngrx/router-store' 

```

```javascript

// optimizing data strucutures with entities - think of ngrx/store as just a client database (convert action.payload which is an array of object to entities where the key of the object will equal the id of the object). look at the pizzas.reducer.ts to see how its done with a reduce function which converts the array into pure object.

entities: { [id: number] : Pizza}

const pizza: any = {
  1: {
    id: 1,
    name: 'pizza',
    toppings: []
  }
}

```

```javascript

// selectors in index.ts
// more on selectors https://toddmotto.com/ngrx-store-understanding-state-selectors

export const getPizzasEntities = createSelector(
  getPizzaState,
  fromPizza.getPizzasEntities
);

export const getAllPizzas = createSelector(
  getPizzasEntities,
  (entities) => {
    return Object.keys(entities).map(id => entities[parseInt(id, 10)]);
  }
);

```

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
