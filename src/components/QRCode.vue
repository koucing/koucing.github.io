
<template>
    <img src="https://api.paylibo.com/paylibo/generator/czech/image?accountNumber=2401457211&bankCode=2010&amount=800.00&currency=CZK&vs={{variable_symbol}}&message=Koucovani" />
</template>

 
<script lang="ts">
import { ref, defineComponent } from 'vue'
const show = ref(false)
 
export default defineComponent({
  name: 'TurnstileVerification',
  setup() {
    const data = ref({
        variable_symbol: "1",
    })
    return { data, show }
    }
})

</script>
