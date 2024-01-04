<template>
  <q-item class="box" :style="{ background: gradientColor }" :to="directory">
    <q-img
      :src="image"
      style="
        display: flex;
        flex-direction: table-column;
        height: 100px;
        width: 60px;
      "
    />
    <q-item class="labelbox">
      <q-item-label class="label">{{ label }}</q-item-label>
    </q-item>
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

    colorType: {
      type: String,
      default: 'redgreen',
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
  computed: {
    gradientColor() {
      const first =
        this.color == 'redgreen'
          ? this.redGreen()
          : this.color == 'yellowpurple'
          ? this.yellowPurple()
          : this.orangeBlue();
      const second =
        this.color == 'redgreen'
          ? this.redGreen1()
          : this.color == 'yellowpurple'
          ? this.yellowPurple1()
          : this.orangeBlue1();
      return `linear-gradient(135deg, ${first}, ${second})`;
    },
  },
  methods: {
    redGreen() {
      return '#FFCCCC';
    },

    redGreen1() {
      return '#98FB98';
    },

    yellowPurple() {
      return '#FFFFE0';
    },

    yellowPurple1() {
      return '#B19CD9';
    },

    orangeBlue() {
      return '#FFDAB9';
    },

    orangeBlue1() {
      return '#ADD8E6';
    },
  },
});
</script>
