# Práctica 4.2 Cálculo de especificidad en CSS 

## Parte 1

Dado un archivo HTML y el CSS correspondiente en el que tenemos las siguientes declaraciones, determinar cuál es la puntuación por especificidad cuando proceda, cuál es la regla ganadora, de qué color se visualizará el texto y por qué: 

```html
<div> 
  <div class="destacado"> 
   <p> párrafo </p> 
   </div>  
</div>
```


| Declaraciones                                                                 | Puntuación especificidad | Regla ganadora, color del texto y por qué                                         |
|------------------------------------------------------------------------------|--------------------------|----------------------------------------------------------------------------------|
| `body {color: grey;}`<br>`body div.destacado p {color: cyan;}`<br>`.destacado {color: green;}`<br>`div.destacado {color: blue;}`<br>`div.destacado p {color: yellow;}`<br>`div:first-child {color: magenta;}` |                          |                                                                                  |
| `body {color: grey;}`<br>`.destacado {color: green;}`                         |                          |                                                                                  |
| `body div.destacado p {color: cyan;}`<br>`.destacado {color: green !important;}` |                          |                                                                                  |
| `body div.destacado p {color: cyan;}`<br>`.destacado {color: green;}`<br>`p {color: blue;}` |                          |                                                                                  |
| `body div.destacado p {color: cyan;}`<br>`.destacado {color: green;}`<br>`p {color: blue !important;}` |                          |                                                                                  |


## Parte 2

### Ejercicio 2.1

Dado el siguiente código HTML:

```html
<div id="contenedor" class="resaltado"> 
    Este es un contenedor resaltado. 
</div> 
```

Y su correspondiente CSS:

```css
#contenedor { 
    color: blue; } 

.resaltado { 
    color: red;  } 
```

¿De qué **color** será el texto dentro de `<div id="contenedor" class="resaltado">`? 


### Ejercicio 2.2

Dado el siguiente código HTML:

```html
<p class="texto-importante">  
Este es un párrafo muy importante.  
</p> 
```

Y su correspondiente CSS:

```css
p { color: green;  }  
 
.texto-importante { 
color: orange; }  
 
body p.texto-importante {  
color: purple;  
} 
```

¿De qué **color** será el texto dentro de `<p class="texto-importante">`?

### Ejercicio 2.3

Dado el siguiente código HTML:

```html
<a href="https://ejemplo.com" class="link-rojo especial"> Este es un enlace importante.  
</a> 
```

Y su correspondiente CSS:

```css
a.link-rojo { color: red; }  
.especial { color: blue; }  
a:hover { color: green; }  
```

 ¿De qué **color** será el enlace cuando el usuario pase el ratón sobre él? 

 ### Ejercicio 2.4

 Dado el siguiente código HTML:

```html
<div id="menu"> <ul>  
<li class="activo">Inicio</li>  
<li>Servicios</li>  
<li>Contacto</li>  
</ul>  
</div> 
```

Y su correspondiente CSS:

```css
#menu ul li { color: gray; }  
#menu .activo { color: blue; }  
#menu ul li.activo { color: red; } 
```

 ¿De qué color será el texto del primer **li** (que tiene la clase activo) dentro de `<div id="menu">`? 

 ### Ejercicio 2.5

 Dado el siguiente código HTML:

```html
<div class="principal"> <p>Primer párrafo en principal.</p> <div class="secundario"> <p>Párrafo en secundario.</p> </div> </div>  
```

Y su correspondiente CSS:

```css
.principal p { font-weight: bold; color: blue; }  
.principal > p { color: green; } 
```

¿Cuál será el color y el grosor de fuente del texto en ambos párrafos? 