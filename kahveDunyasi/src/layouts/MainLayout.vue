<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title> Kahve Dünyası</q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <q-item-label header> Essential Links </q-item-label>
        <component-link
          v-for="link in componentLinks"
          :key="link.title"
          v-bind="link"
        >
        </component-link>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import ComponentLink, {
  ComponentLinkProps,
} from 'components/ComponentLink.vue';

const componentLinks: ComponentLinkProps[] = [
  {
    title: 'Sepet',
    caption: 'Kahve Dünyası',
    icon: 'school',
    link: '/comp1',
  },
  {
    title: 'Giriş',
    caption: 'Kahve Dünyası',
    icon: 'code',
    link: '/comp2',
  },
  {
    title: 'Menü',
    caption: 'Kahve Dünyası',
    icon: 'chat',
    link: '/comp3',
  },
  {
    title: 'Kahve Çikolata Aksesuar',
    caption: 'Kahve Dünyası',
    icon: 'record_voice_over',
    link: '/comp4',
  },
  {
    title: 'Kurumsal Hediyeler',
    caption: 'Kahve Dünyası',
    icon: 'rss_feed',
    link: '/comp5',
  },
 
];

const leftDrawerOpen = ref(false);

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value;
}
</script>
