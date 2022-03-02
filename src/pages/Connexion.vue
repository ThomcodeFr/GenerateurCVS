<template>
  <div class="connexion">
    <h1>Connexion</h1>
    <input v-model="pseudo" placeholder="pseudo" />  <br>
    <input v-model="password" type="password" placeholder="password" />
    <button @click="saveConnexion">Connexion</button>
  </div>
</template>

<script>
import { mapMutations } from 'vuex'
export default {
  name: 'ConnexionForm',
  data: function () {
    return {
      pseudo: '',
      password: '',
    }
  },

  methods: {
    ...mapMutations(['setPseudo']),
    ...mapMutations(['setPassword']),
    saveConnexion() {
      this.setPseudo(this.pseudo);
      this.setPassword(this.password);

      if (this.pseudo == 'pseudo' && this.password == 'password') {
        alert("C'est gagné")
      } else {
        alert("Perdu !");
      }
    },
  },
}
</script>
