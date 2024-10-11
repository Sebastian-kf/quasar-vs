<script setup>
import { ref } from 'vue'

const leftDrawerOpen = ref(false)
const rightDrawerOpen = ref(false)

function toggleLeftDrawer () { leftDrawerOpen.value = !leftDrawerOpen.value }

</script>

<template>
  <q-layout view="hHh lpR fFf">
    <q-header
      reveal
      elevated
      class="bg-primary text-white"
      height-hint="98"
    >
      <q-toolbar>
        <q-btn
          dense
          flat
          round
          icon="menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>
          Quasar playground
        </q-toolbar-title>

        <q-btn
          dense
          flat
          round
          icon="menu"
          @click="toggleRightDrawer"
        />
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      side="left"
      bordered
    >
      <!-- drawer content -->
    </q-drawer>

    <q-drawer
      v-model="rightDrawerOpen"
      show-if-above
      side="right"
      bordered
    >
      <!-- drawer content -->
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer
      elevated
      class="bg-grey-8 text-white"
    >
      <q-toolbar class="flex-center">
        <q-btn
          flat
          color="deep-orange-5"
          icon="person"
        />
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>
