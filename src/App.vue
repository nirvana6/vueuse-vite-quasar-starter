<template>
  <div id="app">
    <img src="./logo.svg" />
    <h1>Hello <a href='https://github.com/vuejs/vite' target='__blank'>Vite</a> and <a
        href='https://github.com/vueuse/vueuse' target='__blank'>VueUse</a>!</h1>

    <h3>Mouse: {{ x }} x {{ y }}</h3>
    <h3>
      Counter: {{ count }}
      <a @click='inc()' style='margin-right:10px'>+</a>
      <a @click='dec()'>-</a>
    </h3>

    <br><br>
    <p><a href='https://github.com/vueuse/vueuse-vite-starter' target='__blank'>Source</a></p>
    <p><a href='https://vueuse-vue3-example.netlify.app/' target='__blank'>Webpack Example</a></p>
  </div>

  <div class="q-pa-md q-gutter-sm">
    <q-editor v-model="editor" min-height="5rem" />

    <q-card flat bordered>
      <q-card-section>
        <pre style="white-space: pre-line">{{ editor }}</pre>
      </q-card-section>
    </q-card>

    <q-card flat bordered>
      <q-card-section v-html="editor" />
    </q-card>
  </div>

</template>

<script setup lang="ts">
import { useMouse, useCounter } from '@vueuse/core'
import { ref } from 'vue'

const { x, y } = useMouse()
const { count, inc, dec } = useCounter()

let editor = ref('What you see is <b>what</b> you get.');

</script>

<style scoped>
html,
body,
h1,
h2,
h3,
p {
  font-family: 'Noto Serif', serif;
  user-select: none;
}

#app {
  text-align: center;
  color: rgba(0, 0, 0, 0.4);
}

img {
  width: 500px;
}

a {
  color: #41b883;
  text-decoration: none;
  cursor: pointer;
}
</style>
