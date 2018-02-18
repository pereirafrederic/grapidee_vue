<template>
  <div class="c_idee">
    <h2> idée: {{idee.nom}} </h2>
    <h3> {{idee.contenu}} </h3>
    <div>
        <span>
            <ideeIdeeDomaine v-for="domaine in idee.listeDomaine" 
            :key="getRandkey()" :domaine="domaine" :name="getRandkey()"> </ideeIdeeDomaine>     
        </span>
    </div>
    <div>
        <span>
          <ideeIdeeIGrappe v-for="grappe in idee.listeGrappe"
          :key="getRandkey()" :grappe="grappe" :name="getRandkey()"> </ideeIdeeIGrappe>
        </span>
    </div>
    <div>  
        <span>
           <ideeIdeeIdeeE v-for="ideeEl in idee.listeEsclave" 
            :key="getRandkey()" :idee="ideeEl" :name="getRandkey()"> </ideeIdeeIdeeE>
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
import IdeeView from './IdeeView'
import {getRandidee} from '../function/RandomIdent'

export default {
  name: 'IdeeIdeeView',
  methods: {
    getRandkey () {
      return getRandidee()
    }
  },
  components: {
    ideeIdeeDomaine: DomaineView, ideeIdeeIGrappe: GrappeView, ideeIdeeIdeeE: IdeeView
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
   display: flex;
   border: 2px solid;
}
</style>
