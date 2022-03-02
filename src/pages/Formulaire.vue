<template>
  <div class="formulaire">
    <h1>Formulaire</h1>
    <div>
      <h2>Formation</h2>
      <p>Nom de la formation</p>
      <input v-model="nomFormation" />
      <br />
      <button @click="saveFormation('nomFormation')">Enregistrer</button>
    </div>
    <table>
      <thead>
        <tr>
          <th>Nom de la formation</th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="formationTab in formationTabs"
          :key="formationTab.saveFormation"
        >
          <td>{{ formationTab.nomFormation }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
export default {
  data() {
    return {
      formationTabs: [''],
    }
  },
  methods: {
    saveFormation: function (message) {
      this.formationTab = message
      alert('vous avez une nouvelle formation: ' + this.nomFormation)
    },
  },
}
</script>
<style></style>
