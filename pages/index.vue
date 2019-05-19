<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <h1 class="my-4 display-3">素因数分解</h1>
      <v-text-field v-model="n" label="分解する数値" />
      <v-btn color="info" depressed block @click="factorization">分解</v-btn>
      結果：{{ formatted }}
    </v-flex>
  </v-layout>
</template>

<script>
import Factorization from 'factorization'

export default {
  data() {
    return {
      n: 1,
      result: []
    }
  },
  computed: {
    formatted() {
      return this.result.join(' x ')
    }
  },
  methods: {
    factorization() {
      this.result = Factorization(this.n)
    }
  }
}
</script>
