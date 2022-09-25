# AlpineJS scope and state management
AlpineJS requires components to be tagged with a `x-data` in order for
the library to attach methods and listeners to the component.

Inner components can access outer component data. The methods and
attributes for a component can be directly written in `x-data` However,
it is much easier to keep track of things by defining a script tag or
separate JavaScript file that contains all of the `x-data` methods and
attributes ect.

However, `x-data` is limited to only the component that it is being
defined. `Alpine.store` provides a global data access across all
components. The syntax definition is *slightly* different.

```
//x-data
Alpine.data('dropdown', () => ({
            open: false,

            toggle() {
                this.open = ! this.open
            }
}))

//store
Alpine.store('darkMode', {
    on: false,

    toggle() {
        this.on = ! this.on
    }
})
```

When using a script tag only for Alpine, you are required to wrap the
definitions in a `document.EventListener('alpine:init',() =>{})`. From
there, you can reference store and data objects from each other using
`Alpine.store('storename')` or `Alpine.data('dataname')`. This is
important because the docs mainly reference store objects from
**outside** the definitions as `$store.storename`. Using this inside
`Alpine.store` will not work.

AlpineJS state management is pretty straight forward otherwise. You are
allowed to define multiple stores I believe as well as data
contexts.

Tags:

    #AlpineJS #scope #state

