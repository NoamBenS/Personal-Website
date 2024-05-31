<template>
  <q-item class="skillbox" :style="{ background: 'gray' }">
    <div>
      <div>
        <q-item class="skilllabelbox">
          <q-item-label class="label">{{ label }}</q-item-label>
        </q-item>
      </div>
      <q-item class="textbox">{{ text }}</q-item>
    </div>
  </q-item>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'SkillsBox',
  props: {
    label: {
      type: String,
      default: '',
    },
    text: {
      type: String,
      default: 'under construction',
    },
  },
});
</script>
