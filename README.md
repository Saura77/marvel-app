# marvel-app

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).


Esta es una aplicación Vue.js simple. Cuenta con 3 componentes anidados entre sí, que utilizan los bindings necesarios para el traspaso de información y que tienen su ciclo de vida determinado. 
Esta app realiza peticiones a la api de marvel, la cual devuelve información acerca de los personajes de la compañía. Los componentes de la app son los siguientes:

App.vue -> componente principal.
CharacterList.vue -> componente encargado de desplegar una lista de los personajes. 
CharacterDetail.vue -> componente encargado de desplegar información del personaje seleccionado (nombre e imagen)
