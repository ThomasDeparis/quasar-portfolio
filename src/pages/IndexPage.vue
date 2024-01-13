<template>
  <q-page class="flex flex-center">
    <div class="row">
      <text-card>
        <template v-slot:title>À propos</template>

        <p>Bonjour ! Moi c'est Thomas.</p>
        <p></p>
        <p>
          Après avoir travaillé sur différents projets d'ampleur dans des ESN
          (entreprises de services numériques), puis dans une startup, j'ai créé
          mon entreprise afin de devenir développeur indépendant.
        </p>
        <p>
          Les missions auxquelles j'ai participé m'ont appris à comprendre et
          m'adapter rapidement aux enjeux métier, nécessaires pour fournir des
          applications et services réellement utiles. Sans quoi, on a beau créer
          une application complète ou technique, si elle ne correspond pas au
          réel besoin client, c'est du temps perdu !
        </p>
        <p>
          J'ai eu l'occasion de travailler dans le retail, le domaine bancaire,
          les télécommunications, la conciergerie, la signature et l'envoi
          électroniques de documents.<br />
          Chaque mission m'a confronté à des défis différents en terme d'enjeux
          et de gestion de projet.
        </p>
        <br />
        <p>
          Que vous soyez un artisan indépendant ou une grande entreprise, j'ai
          la polyvalence pour m'adapter à VOS besoins.
        </p>
      </text-card>
    </div>

    <section-title>Votre besoin</section-title>
    <div class="row">
      <text-card>
        <template v-slot:title>Web vitrine / e-commerce</template>
        <p>
          Besoin de mettre en avant votre nouvelle entreprise ? Un coup de neuf
          sur votre site vieillissant ? Ou proposer vos produits directement en
          ligne ?
        </p>
        <p>
          Je peux vous aider à imaginer le site parfait pour vous. De la
          réalisation jusqu'au suivi et l'hébergement, je me charge de tout.
        </p>
      </text-card>
      <text-card>
        <template v-slot:title>Application sur-mesure</template>
        <p>
          Malgré vos recherches, vous ne trouvez pas d'application qui répond
          EXACTEMENT à votre besoin métier ?
        </p>
        <p>
          N'hésitez pas à me consulter pour définir ensemble votre besoin, et
          construire une application moderne qui améliore votre productivité.
        </p>
      </text-card>
      <text-card>
        <template v-slot:title>Grands comptes - prestation</template>
        <p>Pour des missions de longue durée (> 1 an) en tant que freelance.</p>
        <p>
          Sur site dans la métropole lilloise, ou autour de Lens ou de Douai.À
          distance dans toute la France (déplacements ponctuels possibles).
        </p>
        <p>Pour obtenir mon CV détaillé, merci de me contacter par email.</p>
      </text-card>
    </div>
    <div class="row flex-center q-ma-md">
      <contact-button></contact-button>
    </div>

    <section-title>Quelques réalisations annexes</section-title>
    <div class="row">
      <demo-card
        imgSrc="photo-demo-3r.png"
        demoLink="https://demos.webappsolutelystudios.fr/runranrun"
        :stickers="['Vue.Js 2', 'Quasar']"
      >
        <template v-slot:title>Run Ran Run</template>
        Run Ran Run est une application web ludique et motivante pour gérer les
        réclamations client.
      </demo-card>
      <demo-card imgSrc="photo-rar-gestion.png" :stickers="['C#', 'MySQL']">
        <template v-slot:title>RAR Gestion</template>
        Réalisation d’une application back office Windows pour l’entreprise
        Roues Artisanales.
      </demo-card>
      <!-- <demo-card
        imgSrc="photo-demo-suivi-pea.png"
        demoLink="https://demos.webappsolutelystudios.fr/suivipea"
        :stickers="['Vue.Js 3', 'Quasar', 'Pinia', 'Firebase']"
      >
        <template v-slot:title>Suivi PEA</template>
        Application pour obtenir des informations temps réel sur les actions
        boursières, et enregistrer son portefeuille boursier.
      </demo-card> -->
    </div>

    <!-- footer -->
    <div class="row fit bg-primary justify-center q-mt-xl">
      <q-img src="brandlogo.png" width="80px" height="80px" class="row q-my-sm">
      </q-img>
      <div class="row fit justify-center text-secondary">
        Réalisé avec Vue.Js 3 et Quasar
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent, inject } from "vue";
import TextCard from "../components/TextCard.vue";
import ContactButton from "../components/ContactButton.vue";
import SectionTitle from "../components/SectionTitle.vue";
import DemoCard from "../components/DemoCard.vue";

export default defineComponent({
  name: "IndexPage",
  components: {
    TextCard,
    ContactButton,
    SectionTitle,
    DemoCard,
  },

  setup() {
    return {
      contactEmail: inject("contactEmail"),
    };
  },
});
</script>

<style lang="scss" scoped>
main {
  background-color: $secondary;
}
</style>
