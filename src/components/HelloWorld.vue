<template>
  <div class="hello">
    <!-- Título principal que muestra el mensaje pasado como propiedad -->
    <h1>{{ msg }}</h1>

    <!-- Texto introductorio con un enlace a la documentación de vue-cli -->
    <p>
      Para una guía y recetas sobre cómo configurar y personalizar este proyecto,<br>
      consulta la
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">documentación de vue-cli</a>.
    </p>

    <!-- Sección con plugins instalados -->
    <h3>Plugins CLI Instalados</h3>
    <ul>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel" target="_blank" rel="noopener">babel</a></li>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint" target="_blank" rel="noopener">eslint</a></li>
    </ul>

    <!-- Sección con enlaces esenciales para Vue.js -->
    <h3>Enlaces Esenciales</h3>
    <ul>
      <li><a href="https://vuejs.org" target="_blank" rel="noopener">Documentación Principal</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank" rel="noopener">Foro</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank" rel="noopener">Chat Comunitario</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank" rel="noopener">Twitter</a></li>
      <li><a href="https://news.vuejs.org" target="_blank" rel="noopener">Noticias</a></li>
    </ul>

    <!-- Sección con enlaces al ecosistema de Vue.js -->
    <h3>Ecosistema</h3>
    <ul>
      <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
      <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
      <li><a href="https://github.com/vuejs/vue-devtools#vue-devtools" target="_blank" rel="noopener">vue-devtools</a></li>
      <li><a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">awesome-vue</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld', // Nombre del componente
  props: {
    msg: String // Propiedad que recibe un mensaje (msg) de tipo cadena
  }
}
</script>

<!-- Estilos específicos para este componente -->
<style scoped>
h3 {
  margin: 40px 0 0; /* Margen superior de 40px para los encabezados de nivel 3 */
}
ul {
  list-style-type: none; /* Elimina los puntos de la lista */
  padding: 0; /* Elimina el padding */
}
li {
  display: inline-block; /* Muestra los elementos de la lista en línea */
  margin: 0 10px; /* Espaciado horizontal de 10px entre los elementos */
}
a {
  color: #42b983; /* Color verde para los enlaces */
}
</style>

