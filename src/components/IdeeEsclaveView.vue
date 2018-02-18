<template>
  <div class="c_idee">
    <h2> idée esclave: {{idee.nom}} </h2>
    <h3> {{idee.contenu}} </h3>
    <div>
        <span >
            <ideeEDomaine v-for="domaine in idee.listeDomaine" 
            :key="getRandkey()" :domaine="domaine" :name="getRandkey()"> </ideeEDomaine>     
        </span>
    </div>
    <div>
        <span>
          <ideeEGrappe v-for="grappe in idee.listeGrappe" 
          :key="getRandkey()" 
          :grappe="grappe" 
          :name="getRandkey()"> </ideeEGrappe>
        </span>
    </div>
    <div>  
        <span >
           <ideeEIdee v-for="ideeEl in idee.listeEsclave" 
           :key="getRandkey()" :idee="ideeEl" :name="getRandkey()"> </ideeEIdee>
        </span>
    </div>
    <div class="c_badge">
        <span v-if="idee.tag != null">
        {{idee.tag.nom}}
        </span>
        <span v-for="badge in idee.listeBadge">
          {{badge.nom}}
        </span>
    
    </div>
  </div>
</template>
<script>

import DomaineIdeeView from './DomaineIdeeView'
import GrappeView2 from './GrappeIdeeView'
import IdeeIdeeView from './IdeeIdeeView'
import {getRandidee} from '../function/RandomIdent'

export default {
  name: 'IdeeEsclaveView',
  methods: {
    getRandkey () {
      return getRandidee()
    }
  },
  components: {
    ideeEDomaine: DomaineIdeeView, ideeEGrappe: GrappeView2, ideeEIdee: IdeeIdeeView
  },
  props: {
    idee: {default: {}}
  }
}
</script>

<style scoped>
c_idee {
  text-align: center;
   color: #42b983;
}
</style>