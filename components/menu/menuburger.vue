<template>
  <div class="text-center">
    <v-menu offset-y>
      <template v-slot:activator="{ on }">
        <v-btn
          color="primary"
          dark
          v-on="on"
        >
          Dropdown
        </v-btn>
      </template>
      <v-list>
        <v-list-item
          v-for="(route, index) in listRoute"
          :key="index"
          @click="changePage(route.path)"
        >
          <v-list-item-title>{{ route.name }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
  </div>
</template>

<script>
export default {
    data: function() {
        return {
            listRoute: this.$store.state.routenavbar.listRoute
        };
    },
    methods: {
        changePage(path) {
            next(path);
        }
    }
}
</script>