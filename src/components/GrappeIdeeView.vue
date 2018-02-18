<template>
  <div class="c_grappe">
        <h2> grappe: {{grappe.nom}}</h2>
       <span>
            <grappeIdeeIdee
                v-for="ideeEl in grappe.listeIdee" 
                :key="getRandkey()" 
                :idee="ideeEl" 
                :name="getRandkey()"
            >
            </grappeIdeeIdee>
        </span>
  </div>
</template>

<script>
 import IdeeIdeeView from './IdeeIdeeView'
 import {getRandidee} from '../function/RandomIdent'

export default {
   name: 'GrappeIdeeView',
   methods: {
     getRandkey () {
       return getRandidee()
     }
   },
   props: {
     grappe: {default: {}}
   },
   components: {
     grappeIdeeIdee: IdeeIdeeView
   }
}
</script>

<style scoped>
c_grappe {
  color: #FFFF;
  margin-top: 60px;
}
</style>