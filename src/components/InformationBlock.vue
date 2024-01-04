<template>
  <q-item
    class="box"
    v-bind:style="{ backgroundColor: color }"
    :color="color"
    :to="directory"
  >
    <q-img
      :src="image"
      style="
        display: flex;
        flex-direction: table-column;
        height: 100px;
        width: 60px;
      "
    />
    <q-item-label>{{ label }}</q-item-label>
  </q-item>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'InfromationBlock',
  props: {
    image: {
      type: String,
      default: '',
    },

    color: {
      type: String,
      default: 'black',
    },

    label: {
      type: String,
      default: '',
    },

    directory: {
      type: String,
      default: '/',
    },
  },
});
</script>
