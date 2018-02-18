<template>
  <div>
    <h1 class="c_nom">{{ nom_appli }}</h1>
    <h2 class="c_slogan"> {{slogan}}</h2>    
        <div >
            <ideePrincipale 
                :idee="this.idee" 
                :key="getRandkey()"
            :name="getRandkey()" > </ideePrincipale>
        </div> 
  </div>
</template>

<script>

import IdeeView from './IdeeView'
import {getRandidee} from '../function/RandomIdent'

const urlIdeeProjet = 'http://localhost:9000/grapidee/idee/1?niveauInferieur=6'

export default {
  name: 'home_page',
  data () {
    return {
      nom_appli: 'GRAPIDEE',
      slogan: `une grappe d'idée pour organiser ses idées`,
      idee: {}
    }
  },
  components: {
    ideePrincipale: IdeeView
  },
  methods: {
    getRandkey () {
      return getRandidee()
    },
    loadIdee () {
      var me = this
      fetch(urlIdeeProjet)
      .then(response => response.json())
      .then(data => {
        me.idee = data
      })
    }
  },
  created () {
    this.loadIdee()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
c_titre {
  text-align: center;
  border: 5px;
}
c_slogan {
  text-align: center;
   color: #42b983;
}
</style>
