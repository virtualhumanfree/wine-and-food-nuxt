<template>
    <v-app>
      <Navbar />
      <nuxt />
    </v-app>
</template>

<script>
import Navbar from '@/components/navbar/navbar'

export default {
  components: {
    Navbar
  }
}
</script>
