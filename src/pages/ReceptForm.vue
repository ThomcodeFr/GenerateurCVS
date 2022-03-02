<template>
  <div class="answer">
    <br><button @click="receptPseudo">Voir votre pseudo</button>
    <h2>Hello {{ pseudo }} !</h2>

  </div>
</template>

<script>

import { mapState } from 'vuex';

export default {
  name: 'HelloWorld',
  data: function () {
    return {
      pseudo:'',
    }
  },
  computed: {
    ...mapState(['pseudo'])
  },
  methods: {
    receptPseudo() {
      alert('Voici votre pseudo : ' + this.pseudo)
      this.pseudo(this.pseudo)
    },
  },
}
</script>
<style scoped>
.answer {
  text-align: center;
}
</style>
