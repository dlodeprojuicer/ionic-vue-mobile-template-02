<template>
  <ion-app>
    <h4 class="not-mobile">
      Template is built for mobile, for best experience please use a mobile device or use the browser in mobile mode.
    </h4>
    <ion-router-outlet />
    <Footer :data="footer" v-if="!homePage" @goto="goto" />
    <Footer2 :data="footer" v-if="homePage" @goto="goto" />
  </ion-app>
</template>

<script>
import { IonApp, IonRouterOutlet } from '@ionic/vue';
import { defineComponent } from 'vue';
import { home, notifications, person, card } from "ionicons/icons";

import Footer from "./components/Footer";
import Footer2 from "./components/Footer2";

export default defineComponent({
  name: 'App',
  components: {
    IonApp,
    IonRouterOutlet,
    Footer,
    Footer2
  },
  computed: {
    homePage() {
      return true;
      // return this.store.getters.toggleFooter;
    }
  },
  setup() {
    return {
      home,
      notifications,
      person,
      card
    }
  },
  data() {
    return {
      loggedIn: true,
      footer: [
        {
          label: "Home",
          route: "home",
          icon: home
        },
        {
          label: "Notifications",
          route: "notifications",
          icon: notifications
        },
        {
          label: "Profile",
          route: "profile",
          icon: person
        }
      ]
    }
  },
  methods: {
    goto(route) {
      this.$router.push(route);
    }
  }
});
</script>
