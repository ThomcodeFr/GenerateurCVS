<template>
  <div>
    <Header />
    <Master />
    <button v-on:click="say('accueil')">Accueil</button>
    <!-- <button v-on:click="say('formulaire')">formulaire</button> -->
    <button v-on:click="say('apropos')">A propos</button>
    <button v-on:click="say('mentionLegale')">Mention Legale</button>
    <button v-on:click="say('connexion')">Connexion</button>

    <Accueil v-if="pageMenu == 'accueil'" />
    <Formulaire v-if="pageMenu == 'formulaire'" />
    <Apropos v-if="pageMenu == 'apropos'" />
    <MentionLegale v-if="pageMenu == 'mentionLegale'" />
    <Connexion v-if="pageMenu == 'connexion'" />
    <Footer />
  </div>
</template>

<script>
import Master from './pages/Master.vue'
import Accueil from './pages/Accueil.vue'
import Formulaire from './pages/Formulaire.vue'
import Apropos from './pages/Apropos.vue'
import MentionLegale from './pages/MentionLegale.vue'
import Connexion from './pages/Connexion.vue'
import Header from './template/Header'
import Footer from './template/Footer'
import { mapState } from 'vuex'

export default {
  name: 'App',
  components: {
    Accueil,
    Formulaire,
    Apropos,
    MentionLegale,
    Connexion,
    Master,
    Header,
    Footer,
  },

  beforeCreate() {
   function alertplop() {
      alert('Plop')
    }
    setInterval(alertplop, 10000);
    /* clearInterval(alert); */
  },

  computed: {
    ...mapState(['pseudo']),
  },

  data() {
    return {
      pageMenu: 'accueil',
    }
  },

  methods: {
    say: function (message) {
      this.pageMenu = message
    },
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
