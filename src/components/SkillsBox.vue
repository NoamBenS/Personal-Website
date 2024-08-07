<template>
  <q-item class="skillbox" :style="{ background: '#FFDAB9' }">
    <div>
      <q-item class="skilllabelbox">
        <q-item-label class="skilllabel" :style="{ background: background }"
          >{{ label }}
        </q-item-label>
      </q-item>
      <q-item class="skillitemsbox">
        <div v-for="(icon, index) in icons" :key="icon">
          <img :src="iconImages[index]" alt="icon image" class="iconimage" />
          <q-tooltip
            anchor="top middle"
            self="bottom middle"
            :offset="[10, 10]"
          >
            {{ icon }}
          </q-tooltip>
        </div>
      </q-item>
    </div>
  </q-item>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';

export default defineComponent({
  name: 'SkillsBox',
  props: {
    label: {
      type: String,
      default: '',
    },
    icons: {
      type: Array as PropType<string[]>,
      default: () => [],
    },
    iconImages: {
      type: Array as PropType<string[]>,
      default: () => [],
    },
    background: {
      type: String,
      default: 'white',
    },
  },
});
</script>
