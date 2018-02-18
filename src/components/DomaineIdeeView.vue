<template>
  <div class="c_domaine">
        <h2> domaine: {{domaine.nom}}</h2>
        
        <div>
            <span>
                <domaineIGrappe 
                    v-for="grappeEl in domaine.listeGrappe" 
                    :key="getRandkey()" 
                    :grappe="grappeEl" 
                    :name="getRandkey()"
                > 
                </domaineIGrappe>
            </span>
        </div>
        <div>
            <span>
                <domaineIIdee 
                    v-for="ideeEl in domaine.listeEsclave" 
                    :key="getRandkey()" 
                    :idee="ideeEl" 
                    :name="getRandkey()"
                >
                </domaineIIdee>
            </span>
        </div>
  </div>
</template>

<script>

import GrappeIdeeView from './GrappeIdeeView'
import IdeeEsclaveView from './IdeeEsclaveView'
import {getRandidee} from '../function/RandomIdent'

export default {
  name: 'DomaineIdeeView',
  methods: {
    getRandkey () {
      return getRandidee()
    }
  },
  props: {
    domaine: {default: {}}
  },
  components: {
    domaineIGrappe: GrappeIdeeView, domaineIIdee: IdeeEsclaveView
  }
}
</script>

<style scoped>
c_domaine {
  color: #FFFF;
  margin-top: 60px;
}
</style>
