<template>
  <q-item class="skillbox" :style="{ background: '#FFDAB9' }">
    <div>
      <q-item class="skilllabelbox">
        <q-item-label class="skilllabel" :style="{ background: background }"
          >{{ label }}
        </q-item-label>
      </q-item>
      <q-item class="skilltext">
        <p>
          {{ text }}
        </p>
      </q-item>
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
    background: {
      type: String,
      default: 'white',
    },
  },
});
</script>
