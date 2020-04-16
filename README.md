# vueapp

## Pasos para crear el proyecto
#### Creamos el proyecto
    `vue create vueapp'

#### Creamos los componentes que deseemos
- Hay que hacer `export default` del `name` en cada componente
- En `App.vue`, hay que importar el componente y declararlo en components, para poder usarlo

#### Instalamos Axios
    `npm install axios'
- Una vez que axios se haya instalado con éxito, vamos a importarlo dentro de las etiquetas de script de cada componente donde vayamos a usarlo

    `import axios from 'axios'`

- Añadimos la función `data()` que devolverá los datos y la configuramos como `null`
- con `created: function()`guardaremos la respuesta de la API a la variable declarada en `data()`

#### Internacionalización con i18n

	`npm install vue-i18n --save`
- instalamos `i18n`en el directorio donde tenemos configurada la app con Vue
- Creamos una carpeta `lang/locals`dentro de `src` en donde configuraremos Vue-i18n y en donde tendremos los archivos json de cada una de las traducciones

#####Creamos nuestra instancia de Vue-i18n
- el archivo `index.js`que está en `src/lang` 

#####Por último agregamos una instancia a nuestra main app (main.js)
- importamos i18n
`import i18n from './lang'`
- y lo declaramos en el apartado `new Vue()`

#####Como comprobar en los componentes
// HTML Part

`<div>{{ $t('lang.notice.msg') }}</div>`  
o también con
`<div v-bind:title="$t('lang.notice.msg')"></div>`


#####Como cambiar el `lang` de la página
- En `App.vue`hemos añadido un `<div class="locale-changer">`
- y en `data()` hacemos un return de los distintos lenguajes disponibles.





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