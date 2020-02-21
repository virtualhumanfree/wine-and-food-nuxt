<template>
  <div class="overflow-hidden">
    <v-app-bar
      :collapse="!collapseOnScroll"
      :collapse-on-scroll="collapseOnScroll"
      src="https://picsum.photos/1920/1080?random"
      absolute
      color="deep-purple accent-4"
      dark
      scroll-target="#scrolling-techniques-6"
    >
      <!-- <template v-slot:img="{ props }">
        <v-img v-bind="props" gradient="to top right, rgba(55,236,186,.7), rgba(25,32,72,.7)"></v-img>
      </template>-->

      <v-menu offset-y>
        <template v-slot:activator="{ on }">
          <v-app-bar-nav-icon color="primary" dark v-on="on"></v-app-bar-nav-icon>
        </template>
        <v-list>
          <v-list-item v-for="(item, index) in listRoute" :key="index">
            <v-list-item-title>
              <nuxt-link :to="item.path">{{ item.name }}</nuxt-link>
            </v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
      <!-- <v-toolbar-title>Collapsing Bar</v-toolbar-title> -->

      <v-spacer></v-spacer>

      <v-checkbox v-model="collapseOnScroll" color="white" hide-details></v-checkbox>
    </v-app-bar>
    <v-sheet id="scrolling-techniques-6" class="overflow-y-auto" max-height="600">
      <v-container style="height: 64px;"></v-container>
    </v-sheet>
  </div>
</template>

<script>
import menuburger from "@/components/menu/menuburger";

export default {
  data: function() {
    return {
      collapseOnScroll: true,
      listRoute: this.$store.state.routenavbar.listRoute
    };
  },
  methods: {
    changePage(path) {
      next(path);
    }
  },
  components: {
    menuburger
  }
};
</script>

<style>
#scrolling-techniques-6{
  background: wheat;
}
</style>
