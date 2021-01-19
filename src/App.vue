<template>
    <v-app>
        <v-content transition="scroll-y-transition">
            <router-view></router-view>
        </v-content>
    </v-app>
</template>
<script>

export default {
  name: 'App',

  components: {
  },

  data: () => ({
    //
  }),
};
</script>
