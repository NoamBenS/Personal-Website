<template>
  <q-page>
    <div class="main">
      <q-date v-model="model" title="Choose Data Range" range />
      <q-btn
        color="green"
        label="Generate Graphs Using Selected Dates"
        @click="toggleRegister()"
      />
    </div>
    <div v-if="stat.registered" class="row">
      <q-img
        src="public\catsleep.jpeg"
        spinner-color="white"
        style="height: 500px; max-width: 400px"
      />
    </div>
  </q-page>
</template>

<script lang="ts">
import { ref, defineComponent } from 'vue';
import { reactive } from 'vue';
import GraphsActual from 'components/GraphsActual.vue';

export default defineComponent({
  methods: {
    toggleRegister() {
      this.stat.registered = true;
    },
  },
  props: {
    from: {
      type: String,
      default: '2020/07/08',
    },
    to: {
      type: String,
      default: '2020/07/17',
    },
  },
  setup() {
    return {
      stat: reactive({
        registered: false,
      }),
      model: ref({ from: '2020/07/08', to: '2020/07/17' }),
    };
  },
});
</script>
