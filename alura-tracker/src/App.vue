<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-three-quarter">
      <Formulario_ />
    </div>
  </main>
</template>

<script>
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue';
import Formulario_ from './components/Formulario.vue';

export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    Formulario_
  }
});

</script>

<style scoped></style>
