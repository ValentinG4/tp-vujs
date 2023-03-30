<template>
  <h1>My app</h1>
  <div calss="row">
    <div class="column">
      <span v-html="fullUsername"></span>
    </div>
  </div>

  <div class="row">
    <div class="column">
      <form>
        <label for="firstname">Prénom :</label>
        <input
          v-model.lazy="firstName"
          type="text"
          id="firstname"
          name="firstname"
          required
          maxlength=""
          size="10"
        />
        <label for="lastname">Nom de famille :</label>
        <input
          v-model.lazy="lastName"
          type="text"
          id="lastname"
          name="lastname"
          required
          maxlength="15"
          size="10"
        />
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      firstName: null,
      lastName: null,
      edit: true
    }
  },
  computed: {
    fullUsername() {
      console.log('computed');
      if (this.firstName && this.lastName){
        return <strong>Utilisateur connecté : </strong> ${this.firstName} ${this.lastName}
      }
      return '<strong>Utilisateur non défini</strong>'
    }
  },
  methods: {
  }
}
</script>

<style></style>
