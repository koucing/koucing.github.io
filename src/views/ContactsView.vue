<template>
    <div id="app">
      <TurnstileComponent :sitekey="sitekey" @verify="verify"  />
    </div>
    
    <div id="#container"></div>
</template>
  
<script lang="ts">
    import { defineComponent, ref, onMounted } from 'vue'
    import TurnstileComponent from '@astrianz/cfturnstile-vue3'

    export default defineComponent({
        name: 'Contacts',
        components: {
            TurnstileComponent
        },
        setup() {
            const sitekey = ref<string>('0x4AAAAAAADu0tdEcdycayFa');
            const verify = (token: string): void => {
                console.log(`Turnstile token: ${token}`)
            }
            onMounted(() => {
                console.log("Turnstile Mounted")
            });
            return {
                sitekey,
                verify
            }
        }
    })
</script>
