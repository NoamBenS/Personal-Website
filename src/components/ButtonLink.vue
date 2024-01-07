<template>
  <q-item class="linkbox" :style="{ background: color }" :href="link">
    <q-img
      :src="image"
      style="
        display: flex;
        flex-direction: table-column;
        height: 50px;
        width: 50px;
      "
    />
    <q-item class="labelbox">
      <q-item-label class="linklabel">{{ label }}</q-item-label>
    </q-item>
  </q-item>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'ButtonLink',
  props: {
    image: {
      type: String,
      default: '',
    },

    color: {
      type: String,
      default: '#d3d3d3',
    },

    label: {
      type: String,
      default: '',
    },

    link: {
      type: String,
      default: '',
    },
  },
});
</script>
