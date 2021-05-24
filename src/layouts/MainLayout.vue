<template>
  <q-layout view="lHh Lpr lFf" class="main-layout">
    <q-header>
      <q-toolbar class="q-pt-xl q-pb-md">
        <q-btn flat>
          <q-avatar square size="18px">
            <img v-if="title" src="~assets/back.png" />
            <img else src="~assets/user.png" />
          </q-avatar>
        </q-btn>

        <q-space />
        <div v-if="title" class="main-title">{{ title }}</div>
        <img
          v-else
          alt="company logo"
          class="company-logo"
          src="~assets/harwood-logo.png"
        />
        <q-space />

        <q-btn flat @click="leftDrawerOpen = !leftDrawerOpen">
          <q-avatar square size="18px">
            <img src="~assets/hamburger-menu.png" />
          </q-avatar>
        </q-btn>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label header class="text-grey-8">
          Essential Links
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-footer>
      <q-tabs
        v-model="tab"
        indicator-color="transparent"
        active-color="orange-2"
      >
        <q-tab name="widgets" class="q-py-lg" icon="widgets" />
        <q-tab name="list" class="q-py-lg" icon="list" />
        <q-tab
          name="notifications_none"
          class="q-py-lg"
          icon="notifications_none"
        >
          <q-badge color="red" floating>2</q-badge>
        </q-tab>
        <q-tab name="chat" class="q-py-lg" icon="chat" />
        <q-tab name="account_circle" class="q-py-lg" icon="account_circle" />
      </q-tabs>
    </q-footer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from "components/EssentialLink.vue";

const linksData = [
  {
    title: "Docs",
    caption: "quasar.dev",
    icon: "school",
    link: "https://quasar.dev",
  },
  {
    title: "Github",
    caption: "github.com/quasarframework",
    icon: "code",
    link: "https://github.com/quasarframework",
  },
  {
    title: "Discord Chat Channel",
    caption: "chat.quasar.dev",
    icon: "chat",
    link: "https://chat.quasar.dev",
  },
  {
    title: "Forum",
    caption: "forum.quasar.dev",
    icon: "record_voice_over",
    link: "https://forum.quasar.dev",
  },
  {
    title: "Twitter",
    caption: "@quasarframework",
    icon: "rss_feed",
    link: "https://twitter.quasar.dev",
  },
  {
    title: "Facebook",
    caption: "@QuasarFramework",
    icon: "public",
    link: "https://facebook.quasar.dev",
  },
  {
    title: "Quasar Awesome",
    caption: "Community Quasar projects",
    icon: "favorite",
    link: "https://awesome.quasar.dev",
  },
];

export default {
  name: "MainLayout",
  components: { EssentialLink },
  data() {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData,
      tab: "notifications_none",
    };
  },
  computed: {
    title() {
      return this.$route.name ? this.$route.name : "";
    },
  },
};
</script>

<style lang="scss">
.main-layout {
  .q-header {
    background: transparent;
    .q-toolbar {
      background: #153548;
      opacity: 0.8;
      border-radius: 0px 0px 20px 20px;
    }
    .main-title {
      font-family: Roboto;
      font-weight: bold;
      font-size: 14px;
      text-align: center;
      letter-spacing: 1px;
      text-transform: uppercase;
      color: #ffffff;
    }
  }
  .q-footer {
    background: #153548;
    border-radius: 20px 20px 0px 0px;
  }
  .company-logo {
    position: absolute;
    margin-left: auto;
    margin-right: auto;
    left: 0;
    right: 0;
    text-align: center;
    top: 68px;
  }
  .q-tab {
    .q-badge {
      top: 0px;
      right: 0px;
      border-radius: 50%;
      font-size: 10px;
    }
  }
}
</style>
