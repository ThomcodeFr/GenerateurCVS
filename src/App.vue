<template>
  <div>
    <Header />
    <Master />
    <button v-on:click="say('accueil')">accueil</button>
    <button v-on:click="say('apropos')">apropos</button>
    <button v-on:click="say('mentionLegale')">mentionLegale</button>
    <button v-on:click="say('connexion')">connexion</button>

    <Accueil v-if="pageMenu == 'accueil'"/>
    <Apropos v-if="pageMenu == 'apropos'"/>
    <MentionLegale v-if="pageMenu == 'mentionLegale'"/>
    <Connexion v-if="pageMenu == 'connexion'"/>
    <Footer />
  </div>

</template>

<script>
import Master from './pages/Master.vue'
import Accueil from './pages/Accueil.vue'
import Apropos from './pages/Apropos.vue'
import MentionLegale from './pages/MentionLegale.vue'
import Connexion from './pages/Connexion.vue'
import Header from './template/Header'
import Footer from './template/Footer'

export default {
  name: 'App',
  components: {
    Accueil,
    Apropos,
    MentionLegale,
    Connexion,
    Master,
    Header,
    Footer,
  },
  data(){
    return{
      pageMenu : 'accueil'
    }
  },

  methods: {
    say: function (message) {
      this.pageMenu = (message)
    }
  }
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
