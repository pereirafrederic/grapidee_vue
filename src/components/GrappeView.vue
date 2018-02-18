<template>
  <div class="c_grappe">
        <h2> grappe: {{grappe.nom}}</h2>
       <span>
            <grappeIdee
                v-for="ideeEl in grappe.listeIdee" 
                :key="getRandkey()" 
                :idee="ideeEl" 
                :name="getRandkey()"
            >
            </grappeIdee            </grappeIdee>
>
        </span>
  </div>
</template>

<script>
 import IdeeEsclaveView from './IdeeEsclaveView'
 import {getRandidee} from '../function/RandomIdent'

export default {
   name: 'GrappeView',
   methods: {
     getRandkey () {
       return getRandidee()
     }
   },
   props: {
     grappe: {default: {}}
   },
   components: {
     grappeIdee: IdeeEsclaveView
   }
}
</script>

<style scoped>
c_grappe {
  color: #FFFF;
  margin-top: 60px;
}
</style>