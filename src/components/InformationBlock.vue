<template>
  <q-item class="box" :style="{ background: gradientColor }">
    <q-expansion-item style="flex-direction: table-row; width: 100%">
      <template v-slot:header>
        <q-item class="labelbox">
          <q-item-label class="label">{{ label }}</q-item-label>
        </q-item>
        <q-space />
        <q-img
          :src="image"
          style="
            max-height: 140px;
            max-width: 510px;
            display: flex;
            flex-direction: table-column;
            border-radius: 10px;
          "
        />
        <q-space />
        <a :href="link" class="githublink">
          <q-img :src="`/icons/techicons/github.png`" class="githubicon" />
        </a>
      </template>

      <q-item class="textbox">{{ text }}</q-item>
    </q-expansion-item>
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
      default: 'redgreen',
    },

    label: {
      type: String,
      default: '',
    },

    text: {
      type: String,
      default: 'under construction',
    },
    link: {
      type: String,
      default: '',
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
