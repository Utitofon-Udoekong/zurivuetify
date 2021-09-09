<template>
  <v-navigation-drawer right app clipped width="320" v-model="showThreadReply">
    <v-toolbar color="#00B87C" class="white--text rounded-tl" flat>
      <v-toolbar-title>Thread</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn icon @click="showThreadReply = !showThreadReply">
        <v-icon color="white">mdi-close</v-icon>
      </v-btn>
    </v-toolbar>
    <v-list>
      <v-list-item three-line>
        <v-list-item-avatar>
          <v-img src="@/assets/woman.png"></v-img>
        </v-list-item-avatar>
        <v-list-item-content>
          <v-list-item-title>MamaGee</v-list-item-title>
          <v-list-item-subtitle>
            Lorem ipsum dolor sit amet, consectetur ipsam consequuntur molestias
            animi.
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
      <span class="d-flex justify-space-between align-center">
        <v-subheader style="color: #999" class="caption"
          >{{ replyCount }} replies</v-subheader
        >
        <v-divider></v-divider>
      </span>
      <template v-for="(item, i) in thread_replies">
        <template>
          <v-list-item :key="i" three-line>
            <v-list-item-avatar>
              <v-img :src="require(`@/assets/${item.userAvatar}`)"></v-img>
            </v-list-item-avatar>

            <v-list-item-content>
              <v-list-item-title v-text="item.userName"></v-list-item-title>
              <v-list-item-subtitle v-html="item.reply"></v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </template>
      </template>
    </v-list>
    <v-card class="mx-3" outlined>
      <v-textarea
        no-resize
        color="#999"
        row-height="20"
        full-width
        rows="2"
        class=""
      ></v-textarea>

      <v-row class="px-2 pb-2 ma-0" justify="space-between">
        <v-btn-toggle borderless>
          <v-btn icon x-small>
            <v-img :src="require('@/assets/zap.png')"></v-img>
          </v-btn>
          <v-divider vertical class="mx-1"></v-divider>
          <v-btn icon x-small>
            <v-img :src="require('@/assets/bold.png')"></v-img>
          </v-btn>

          <v-btn icon x-small class="mx-1">
            <v-img :src="require('@/assets/italics.png')"></v-img>
          </v-btn>
          <v-btn icon x-small>
            <v-img :src="require('@/assets/underline.png')"></v-img>
          </v-btn>
        </v-btn-toggle>

        <v-btn-toggle borderless>
          <v-btn icon x-small>
            <v-img :src="require('@/assets/smile.png')"></v-img>
          </v-btn>
          <v-btn icon x-small class="mx-1">
            <v-img :src="require('@/assets/paperclip.png')"></v-img>
          </v-btn>

          <v-btn icon x-small>
            <v-icon color="#999">mdi-navigation-outline</v-icon>
          </v-btn>
          <v-divider vertical class="mx-1"></v-divider>

          <v-btn icon x-small>
            <v-icon color="#999">mdi-chevron-down</v-icon>
          </v-btn>
        </v-btn-toggle>
      </v-row>
    </v-card>
    <v-checkbox label="Also send as direct message"></v-checkbox>
  </v-navigation-drawer>
</template>

<script>
export default {
  name: "ThreadReplySidebar",
  props: {
    showThreadReply: Boolean,
  },
  data() {
    return {
      thread_replies: [
        {
          userName: "MamaGee",
          timeStamp: "6:06pm",
          reply:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit. quia id doloribus inventore blanditiis?",
          userAvatar: "woman.png",
        },
        {
          userName: "PapaGee",
          timeStamp: "6:07pm",
          reply:
            "Lorem ipsum dolor sit amet, consectetur adipisicing elit. quia id doloribus inventore blanditiis?",
          userAvatar: "man.png",
        },
      ],
    };
  },
  computed: {
    replyCount() {
      return this.thread_replies.length;
    },
  },
};
</script>

<style>
</style>