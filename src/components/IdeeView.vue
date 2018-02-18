<template>
  <div class="c_idee">
    <h2> idée: {{idee.nom}} </h2>
    <h3> {{idee.contenu}} </h3>
    <div>
        <span>
            <ideeDomaine v-for="domaine in idee.listeDomaine" 
            :key="getRandkey()" :domaine="domaine" :name="getRandkey()"> </ideeDomaine>     
        </span>
    </div>
    <div>
        <span>
          <ideeGrappe v-for="grappe in idee.listeGrappe"
          :key="getRandkey()" :grappe="grappe" :name="getRandkey()"> </ideeGrappe>
        </span>
    </div>
    <div>  
        <span>
           <ideeIdeeE v-for="ideeEl in idee.listeEsclave" 
            :key="getRandkey()" :idee="ideeEl" :name="getRandkey()"> </ideeIdeeE>
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

import DomaineView from './DomaineView'
import GrappeView from './GrappeView'
import IdeeEsclaveView from './IdeeEsclaveView'
import {getRandidee} from '../function/RandomIdent'

export default {
  name: 'IdeeView',
  methods: {
    getRandkey () {
      return getRandidee()
    }
  },
  components: {
    ideeDomaine: DomaineView, ideeGrappe: GrappeView, ideeIdeeE: IdeeEsclaveView
  },
  props: {
    idee: {default: {}}
  }
}
</script>
<style scoped>
c_idee {
   textAlign: center;
   color: #42b983;
   diplay: inline-block;
   border: 2px solid;
   
}
</style>
