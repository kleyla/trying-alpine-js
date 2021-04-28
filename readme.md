# ALPINE JS

```html
<div
  x-data="{name: 'Karen', email: 'kleyla01@live.com'}"
  x-init="name = 'Karen R'"
>
  <p x-text="name"></p>
</div>
```

- `x-data` nos permite tener la informacion que sera usada en el bloque.
- `x-init` al arrancar esto se cargara.
- `x-text` Para indicar que contendra esa etiqueta como innerText.

Tanto `x-data` y `x-init` pueden ser funciones, la primera que retorne los datos, la segunda que altere los datos, por ejemplo:

```html
<div x-data="mainComp()" x-init="start()">
  <p x-text="user"></p>
</div>
<script>
  function mainComp() {
    return {
      user: "hi",
      start: function () {
        console.log("Arranca!");
        this.user = "bye";
      },
    };
  }
</script>
```

## Eventos

- `x-on:click` o su equivalente `@click` son usados para los eventos.
- `x-show` para mostrar u oculta un bloque html en funcion de un valor un condicinal.
- `x-bind` para modificar ciertos atributos html, por ejemplo `class`, `disabled`

```html
<div x-data="main()">
  <p x-text="open"></p>
  <button @click="open = !open">Cambia!</button>
  <p x-show="open">Hola mundo!</p>
  <p x-bind:class="{'active': open, 'inactive': !open}">Parrafo con estilo</p>
  <button x-bind:disabled="open">Pulsa</button>
</div>

<script>
  function main() {
    return {
      open: true,
    };
  }
</script>
```

## Gestion de eventos

Para manejar mas eventos ver [aqui]("./src/index-3.html")
