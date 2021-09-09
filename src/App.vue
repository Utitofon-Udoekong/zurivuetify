<template>
  <v-app style="background: #f6f6f6">
    <v-navigation-drawer app width="250" permanent> </v-navigation-drawer>
    <v-app-bar app color="#f6f6f6" dark flat clipped-right>
      <v-spacer></v-spacer>
      <v-spacer></v-spacer>
      <v-text-field
        hide-details
        outlined
        dark
        dense
        color="#999"
        placeholder="Search here"
      >
        <template v-slot:append>
          <v-icon color="#999">mdi-magnify</v-icon>
        </template>
      </v-text-field>

      <v-btn icon>
        <v-icon color="#999">mdi-crosshairs-gps</v-icon>
      </v-btn>

      <v-btn icon @click="showThreadReply = !showThreadReply">
        <v-avatar color="#00B87C">
          <span class="white--text text-h5">JJ</span>
        </v-avatar>
      </v-btn>
    </v-app-bar>

    <v-main>
      <v-container>
        <v-toolbar color="white" flat class="mb-5">
          <v-avatar>
            <v-img :src="require(`@/assets/woman.png`)"></v-img>
          </v-avatar>
          <v-toobar-title class="text-h6 font-weight-bold ml-3"
            >MamaGee
            <v-icon>mdi-chevron-down</v-icon>
          </v-toobar-title>
          <v-spacer></v-spacer>
          <v-btn class="ma-2" color="black" flat text dark>
            <v-icon dark left> mdi-plus </v-icon>Add Bookmark
          </v-btn>
        </v-toolbar>
        <router-view />
      </v-container>
    </v-main>
    <ThreadReplySidebar :showThreadReply="showThreadReply" />
  </v-app>
</template>

<script>
import ThreadReplySidebar from "@/components/threadReplySidebar.vue";
export default {
  name: "App",
  components: {
    ThreadReplySidebar,
  },
  data() {
    return {
      showThreadReply: true,
    };
  },
};
</script>

<style>
.v-list--three-line .v-list-item .v-list-item__subtitle,
.v-list-item--three-line .v-list-item__subtitle {
  -webkit-line-clamp: unset;
  color: #242424 !important;
  letter-spacing: 0.8px;
}
.v-list-item__title {
  font-weight: 600;
}
/* #242424 */
/* #3A3A3A */
</style>
