<template>
  <div class="containerBody">
    <h1>Nos Vins</h1>
    <div class="containerCard">
      <div v-for="(data, index) in listDataCard" :key="index">
        <v-card class="mx-auto background" max-width="344">
          <v-img v-bind:src="data.image" height="200px"></v-img>

          <v-card-title>{{ data.name }}</v-card-title>

          <v-card-subtitle>{{ data.firstDescription }}</v-card-subtitle>

          <v-card-actions>
            <v-btn text>Voir</v-btn>

            <v-btn color="purple" text>Inscrit toi</v-btn>

            <v-spacer></v-spacer>

            <v-btn icon @click="toggleChevron(data.id)">
              <v-icon>{{ show && numChevron === data.id ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
            </v-btn>
          </v-card-actions>

          <v-expand-transition>
            <div v-show="show && numChevron === data.id">
              <v-divider></v-divider>

              <v-card-text>{{ data.secondDescription }}</v-card-text>
            </div>
          </v-expand-transition>
        </v-card>
      </div>
    </div>
  </div>
</template>