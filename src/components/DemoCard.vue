<template>
  <q-card class="q-ma-md col shadow-10" style="min-width:350px">
    <q-img
      :height="imgHeight"
      fit
      @mouseover="showDemo = true"
      @mouseleave="showDemo = false"
      :src="imgSrc"
    >
      <transition v-if="showDemo" mode="out-in" appear>
        <div class="absolute-full flex flex-center">
          <q-btn v-if="demoLink" flat rounded icon="play_circle_outline" size="xl" :href="demoLink" />
        </div>
      </transition>      
    </q-img>

    <q-card-section>
      <div class="text-center text-h4">
        <slot name="title"></slot>
      </div>
    </q-card-section>
    <q-card-section class="text-body1 section">
      <slot></slot>
    </q-card-section>
    <q-card-section>
      <q-chip v-for="sticker in stickers" :key="sticker"
        color="primary"
        text-color="secondary"
        icon="terminal"
      >
        {{ sticker }}
      </q-chip>
    </q-card-section>

    <q-card-actions vertical align="center" v-if="demoLink">
      <q-btn
        outline
        text-color="primary"
        size="lg"
        icon-right="play_circle_outline"
        label="DEMO"
        :href="demoLink"/>
    </q-card-actions>
  </q-card>
</template>

<script>
import { defineComponent, ref } from "vue"
import { useQuasar } from 'quasar'

export default defineComponent({
  name: 'DemoCard',
  props: {
    demoLink: String,
    imgSrc: String,
    stickers: Array
  },

  setup() {
    const showDemo = ref(false)
    const $q = useQuasar()

    return {
      showDemo,
      imgHeight: $q.platform.is.mobile ? '250px' : '300px'
    }
  }
})
</script>

<style lang="scss" scoped>
.section {
  text-align: justify;
}

.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
