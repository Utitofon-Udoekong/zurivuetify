<template>
  <div>
    <v-card class="text-center pt-5 pb-3" flat>
      <v-menu bottom origin="center center" transition="scale-transition">
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="#999"
            class="rounded-pill"
            outlined
            small
            v-bind="attrs"
            v-on="on"
          >
            <span class="text-subtitle-2">Monday, August 23rd</span>
            <v-icon>mdi-chevron-down</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-item v-for="(item, i) in items" :key="i">
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-card>
    <v-list three-line>
      <template v-for="(item, i) in thread">
        <template>
            <v-list-item :key="i" @contextmenu="alert">
              <v-list-item-avatar>
                <v-img :src="require(`@/assets/${item.userAvatar}`)"></v-img>
              </v-list-item-avatar>
              <v-list-item-content>
                <v-list-item-title>
                  {{ item.userName }}
                  <span
                    class="ml-5 text--disabled font-weight-thin"
                    v-text="item.timeStamp"
                  ></span>
                </v-list-item-title>
                <v-list-item-subtitle>
                  {{ item.message }}
                </v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
        </template>
      </template>
    </v-list>
    <v-card class="text-center pt-5 pb-3 mt-6" flat>
      <v-menu bottom origin="center center" transition="scale-transition" flat>
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="#999"
            class="rounded-pill"
            outlined
            small
            v-bind="attrs"
            v-on="on"
          >
            <span class="text-subtitle-2">Monday, August 23rd</span>
            <v-icon>mdi-chevron-down</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-item v-for="(item, i) in items" :key="i">
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-card>
    <v-list three-line>
      <template v-for="(item, i) in thread2">
        <template>
            <v-list-item :key="i">
              <v-list-item-avatar>
                <v-img :src="require(`@/assets/${item.userAvatar}`)"></v-img>
              </v-list-item-avatar>
              <v-list-item-content>
                <v-list-item-title>
                  {{ item.userName }}
                  <span
                    class="text-caption ml-5 text--disabled font-weight-thin"
                    v-text="item.timeStamp"
                  ></span>
                </v-list-item-title>
                <v-list-item-subtitle>
                  {{ item.message }}
                </v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
        </template>
      </template>
    </v-list>
  </div>
</template>

<script>
export default {
  name: "MessageThread",
  data() {
    return {
      items: [
        { title: "Click Me" },
        { title: "Click Me" },
        { title: "Click Me" },
        { title: "Click Me 2" },
      ],
      thread: [
        {
          userName: "MamaGee",
          timeStamp: "6:06pm",
          message:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit. quia id doloribus inventore blanditiis? consectetur adipisicing elit. quia id doloribus consectetur adipisicing elit. quia id doloribus inventore blanditiis?",
          userAvatar: "woman.png",
        },
        {
          userName: "MamaGee",
          timeStamp: "6:06pm",
          message:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit. quia id doloribus inventore blanditiis? consectetur adipisicing elit. quia id doloribus consectetur adipisicing elit. quia id doloribus inventore blanditiis?",
          userAvatar: "woman.png",
        },
        {
          userName: "MamaGee",
          timeStamp: "6:06pm",
          message:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit. quia id doloribus inventore blanditiis? consectetur adipisicing elit. quia id doloribus consectetur adipisicing elit. quia id doloribus inventore blanditiis?",
          userAvatar: "woman.png",
        },
        {
          userName: "PapaGee",
          timeStamp: "6:07pm",
          message:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit. quia id doloribus inventore blanditiis? consectetur adipisicing elit. quia id doloribus consectetur adipisicing elit. quia id doloribus inventore blanditiis?",
          userAvatar: "man.png",
        },
        {
          userName: "PapaGee",
          timeStamp: "6:07pm",
          message:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit. quia id doloribus inventore blanditiis? consectetur adipisicing elit. quia id doloribus consectetur adipisicing elit. quia id doloribus inventore blanditiis?",
          userAvatar: "man.png",
        },
      ],
      thread2: [
        {
          userName: "PapaGee",
          timeStamp: "6:07pm",
          message:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit. quia id doloribus inventore blanditiis? consectetur adipisicing elit. quia id doloribus consectetur adipisicing elit. quia id doloribus inventore blanditiis?",
          userAvatar: "man.png",
        },
        {
          userName: "MamaGee",
          timeStamp: "6:06pm",
          message:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit. quia id doloribus inventore blanditiis? consectetur adipisicing elit. quia id doloribus consectetur adipisicing elit. quia id doloribus inventore blanditiis?",
          userAvatar: "woman.png",
        },
        {
          userName: "PapaGee",
          timeStamp: "6:07pm",
          message:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit. quia id doloribus inventore blanditiis? consectetur adipisicing elit. quia id doloribus consectetur adipisicing elit. quia id doloribus inventore blanditiis?",
          userAvatar: "man.png",
        },
        {
          userName: "PapaGee",
          timeStamp: "6:07pm",
          message:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit. quia id doloribus inventore blanditiis? consectetur adipisicing elit. quia id doloribus consectetur adipisicing elit. quia id doloribus inventore blanditiis?",
          userAvatar: "man.png",
        },
      ],
    };
  },
  methods:{
    alert(){
      this.alert('mamamam')
    }
  }
};
</script>

<style>
</style>