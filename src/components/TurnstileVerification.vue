<template>
  <Turnstile :sitekey="sitekey" @verify="verify"/>
  <div v-if="data">{{ data }}</div>
</template>

<script lang="ts">
import { defineComponent, ref, defineAsyncComponent } from 'vue'
import type { Ref } from 'vue'
import Turnstile from 'cfturnstile-vue3'
import axios from 'axios'

export default defineComponent({
  name: 'TurnstileVerification',
  components: {
    Turnstile
  },
  setup() {
    const sitekey: Ref<string> = ref('0x4AAAAAAADu0tdEcdycayFa')
    const data: Ref<string | null> = ref("null")

    const loadComponent = (type: string) =>
    defineAsyncComponent(
      () =>
        import(`../components/PersonalInfo.vue`),
    );

    function verify(token: string) {
      console.log(token)
      axios.post('/api/person', { token })
        .then(response => {
          data.value = response.data
        })
        .catch(error => {
          console.error(error)
          data.value = "Nepovedlo se získat data. Můžete prosím opakovat akci později?"
        })

    }

    return {
      data,
      sitekey,
      verify
    }
  }
})
</script>
