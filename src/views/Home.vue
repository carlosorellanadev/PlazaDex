<template>
  <MainDex/>
</template>

<script>

import { defineAsyncComponent } from 'vue'

export default {
  components: {
    MainDex: defineAsyncComponent ( () => import ('../pokedex/layouts/Main.vue' ))
  }
}
</script>
