<template>
  <main>
    <input type="text" v-model="v$.name.$model">
    <pre lang="json">
      {{ v$ }}
    </pre>
  </main>
</template>

<script lang="ts" setup>
import { reactive } from '@nuxtjs/composition-api'
import useVuelidate from '@vuelidate/core'
import { required } from '@vuelidate/validators'

const state = reactive({ name: '' })
const rules = { name: { required } }

const v$ = useVuelidate(rules, state)
</script>
