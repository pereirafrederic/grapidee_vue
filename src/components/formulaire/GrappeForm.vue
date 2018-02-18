<template>
  <div class="grappe_form"> 
      <form action="/ma-page-de-traitement" method="post">
        <div class="form-group" :class="{'has-error': errors.has('email') }" >
            <label class="control-label" for="grappe">nom grappe</label>
            <input v-model.trim="grappeChoisi" v-validate="grappe_valid" data-rules="required|grappe_valid" class="form-control" type="text" placeholder="regroupement grappe">
            <p class="text-danger" v-if="errors.has('grappe_valid')">{{ errors.first('grappe_valid') }}</p>

            <select v-model="domaineChoisi">
                <option disabled value="">Rattaché au domaine ?</option>
                <option v-for="optionDomaine of domaines">optionDomaine.nom</option>
            </select>
        </div> 
      </form>
  </div>
</template>

<script>
export default {
  name: 'GrappeForm',
  methods: {
    getRandkey () {
      return getRandidee()
    }
  },
  data: {
    grappeChoisi : '',
    domaineChoisi : ''
  }
}
</script>

<style scoped>
grappe_form {
  color: #FFFF;
  margin-top: 60px;
}
</style>
