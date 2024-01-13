<template>
  <q-layout view="lhr lpR fFf">
    <q-header elevated>
      <div class="row justify-center">
        <q-img
          src="brandlogo.png"
          :width="brandLogoSize"
          :height="brandLogoSize"
          class="q-mt-sm"
        >
        </q-img>
      </div>
      <div class="row justify-center text-h5 text-secondary q-mb-sm">
        <contact-button transparent :email="contactEmail" />
        <div class="col-1"></div>
        <q-btn
          flat
          size="lg"
          href="https://www.linkedin.com/in/thomas-deparis-0298b8a2"
        >
          <q-avatar rounded>
            <img class="q-pa-sm" src="linkedin-logo.png" />
          </q-avatar>
          LinkedIn
        </q-btn>
      </div>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
    <q-footer>
      <cookie-consent>
        <template v-slot:message>
          <div class="row justify-center q-ma-sm text-body1">
            Ce site n'utilise que des cookies strictement nécessaires, aucune
            donnée n'est partagée à des tiers. Pour plus d'informations,
            <a href="http://cookiesandyou.com">cliquez ici.</a>
          </div>
        </template>
        <template v-slot:button>
          <div class="row justify-center q-ma-md">
            <q-btn
              :color="'secondary'"
              :text-color="'primary'"
              icon-right="thumb_up"
              size="md"
              label="J'ai compris !"
            />
          </div>
        </template>
      </cookie-consent>
    </q-footer>
  </q-layout>
</template>

<script>
import { defineComponent, provide } from "vue";
import { useQuasar } from "quasar";
import ContactButton from "components/ContactButton";
import CookieConsent from "vue-cookieconsent-component";

export default defineComponent({
  name: "MainLayout",
  components: {
    ContactButton,
    CookieConsent,
  },

  setup() {
    // provide contact email for all the app
    const contactEmail = "contact@webappsolutelystudios.fr";
    provide("contactEmail", contactEmail);
    const $q = useQuasar();

    return {
      brandLogoSize: $q.platform.is.mobile ? "100px" : "180px",
      contactEmail,
    };
  },
});
</script>

<style lang="scss">
body {
  font-family: "Open Sans, sans-serif";
}
</style>
