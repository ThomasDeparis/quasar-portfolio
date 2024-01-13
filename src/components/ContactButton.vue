<template>
  <q-btn
    :flat="transparent" 
    :outline="!transparent"
    :text-color="transparent ? 'secondary' : 'primary'"
    icon-right="mail"
    size="lg"
    label="contact"
    :href="emailHref"
   />
</template>

<script>
import { defineComponent } from "vue"

export default defineComponent({
  name: 'ContactButton',
  props: {
    email: String,
    transparent: {
      type: Boolean,
      default: false
    }
  },

  setup(props) {
    return {
        emailHref: 'mailto:' + props.email
    }
  }
})
</script>
