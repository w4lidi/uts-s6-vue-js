<script>
import Liga1 from './assets/Liga1.json'
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import Card from './components/Card.vue'
import CardV2 from './components/CardV2.vue'
import Table from './components/Table.vue'
import Details from './components/Details.vue'


import Flags from './components/Flag.vue'



// Add it to your template


 

export default{
  data(){
    return{
      clubs: Liga1,
      ttt:20,
      shows:false,
    }
  },
  components:{
    Card,
    CardV2,
    Table,
    Details,
    Flags
  },
  methods:{
    det(a){
      this.ttt = a;
    }
  }
}
</script>

<template>
  <div >
<span class="fl star"></span>
    <div class="d-flex flex-wrap justify-content-center ">
      <Card @click="shows = true"  v-for="club in clubs" :key="clubs.id" :clubname="clubs[club.id].clubname" :logopath="clubs[club.id].logopath" @ViewDetails="ttt = club" />
    </div>

  <hr>

    <div v-if="shows" class="">
      <Details :data="ttt" />
      <div class="d-flex flex-wrap justify-content-center ">
      <a href="#" @click="shows = !shows" ><span class="fl af"></span>Hide Details</a>
      </div>
      <hr>
    </div>

    <div>
      <Table/>
    </div>
  </div>
</template>

<style scoped>
wrapper{
  display: grid;
}

header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
