<template>
  <div class="c_domaine">
        <h2> domaine: {{domaine.nom}}</h2>
        
        <div>
            <span>
                <domaineGrappe 
                    v-for="grappeEl in domaine.listeGrappe" 
                    :key="getRandkey()" 
                    :grappe="grappeEl" 
                    :name="getRandkey()"
                > 
                </domaineGrappe>
            </span>
        </div>
        <div>
            <span>
                <domaineIdee 
                    v-for="ideeEl in domaine.listeEsclave" 
                    :key="getRandkey()" 
                    :idee="ideeEl" 
                    :name="getRandkey()"
                >
                </domaineIdee>
            </span>
        </div>
  </div>
</template>

<script>

import GrappeView from './GrappeView'
import IdeeEsclaveView from './IdeeEsclaveView'
import {getRandidee} from '../function/RandomIdent'

export default {
  name: 'DomaineView',
  methods: {
    getRandkey () {
      return getRandidee()
    }
  },
  props: {
    domaine: {default: {}}
  },
  components: {
    domaineGrappe: GrappeView, domaineIdee: IdeeEsclaveView
  }
}
</script>

<style scoped>
c_domaine {
  color: #FFFF;
  margin-top: 60px;
}
</style>
