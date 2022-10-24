<template>
  <v-app app>
    <v-app-bar dark app>
    <v-app-bar-nav-icon
      @click="drawer = true"
      class="d-flex d-sm-none"
    >
    </v-app-bar-nav-icon>
    <template>
      <v-tabs
        v-model="tab"
        align-with-title
        class="d-none d-sm-flex"
      >
        <v-tabs-slider color="green"></v-tabs-slider>
        <v-tab
          v-for="item in items" :key="item"
        >
          {{ item }}
        </v-tab>
      </v-tabs>
    </template>
   </v-app-bar>
   <v-navigation-drawer
    v-model="drawer"
    absolute
    temporary
   >
    <v-list
      nav
      dense
    >
      <v-list-item-group>
        <v-list-item v-for="(item, index) in items" :key="item">
          <v-list-item-title @click="tab = index">
            {{ item }}
          </v-list-item-title>
        </v-list-item>
      </v-list-item-group>
    </v-list>
   </v-navigation-drawer>
    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    drawer: false,
    tab: null,
    items: [
      'Home',
      'Covid-19',
      'About',
      'Contact',
    ]
  }),
};
</script>
