<template>
  <div class="hello">
    <p>Connexion</p>
    <input v-model="pseudo" /> <br />
    <br><button @click="savePseudo">Sauvegarder votre pseudo</button>
  </div>
</template>

<script>
import { mapMutations } from 'vuex'
export default {
  name: 'HelloForm',
  data: function () {
    return {
      pseudo: '',
    }
  },
  methods: {
    ...mapMutations(['setPseudo']),
    savePseudo() {
      alert('saving pseudo into store ' + this.pseudo)
            this.setPseudo(this.pseudo)
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  text-align: center;
}
</style>
