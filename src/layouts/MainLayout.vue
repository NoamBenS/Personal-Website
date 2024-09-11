<template>
  <q-layout view="lHh Lpr lFf">
    <q-header>
      <q-toolbar class="toolbar">
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />
        <q-toolbar-title class="toolbar-title">
          <a href="/" style="text-decoration: none; color: inherit">
            Noam Ben Simon
          </a>
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer class="toolbar" v-model="leftDrawerOpen" bordered>
      <q-list>
        <q-item-label header> Links </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <div class="footer">
      This website and all code were done by me | Icons from
      <a href="https://icons8.com/">icons8</a> | Fonts from
      <a href="https://www.fontspace.com/">fontspace</a> and
      <a href="https://www.dafont.com/">dafont</a>
    </div>
  </q-layout>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import EssentialLink from 'components/EssentialLink.vue';

const linksList = [
  {
    title: 'GitHub',
    caption: 'My Personal GitHub',
    icon: '',
    link: 'https://github.com/NoamBenS',
  },
  {
    title: 'LinkedIn',
    caption: 'Visit My LinkedIn',
    icon: '',
    link: 'https://www.linkedin.com/in/noambensimon/',
  },
];

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink,
  },

  setup() {
    const leftDrawerOpen = ref(false);

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
    };
  },
});
</script>
