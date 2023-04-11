<script lang="ts">
import { defineComponent, ref, defineAsyncComponent } from 'vue'

export default defineComponent({
  name: 'TurnstileVerification',
  setup() {
    const data = ref({
        name: "Jaroslav Henner",
        email: "jaroslav.henner@gmail.com",
        phone: "725 580 001"
    })
    return { data }
    }
})
</script>

<template>
    <div>Jméno: {{ data.name }}</div>
    <div>Email: {{ data.email }}</div>
    <div>Telefon: {{ data.phone }}</div>
</template>