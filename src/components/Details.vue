<script>
	import CardV2 from './CardV2.vue'
	export default{
		data(){
			return{
				
			}
		},
		emits:['view-details'],

		components:{
			CardV2
		},
		props:[
			"data",

			],
		methods:{
			chg(s){
				this.stat = s;
			}
		}
	}
</script>

<template>
	  <div class="d-flex flex-wrap justify-content-center"  >
    <div class="card m-1 border-0  " style="width: 15rem;">
    <img  :src="data.logopath" class="card-img-top " alt="logo">
    <div class="card-body">
	    	<h2  class="text-center" >{{data.clubname}}</h2>
	  	</div>
  </div>
  <div>{{data}}</div>
  <div>{{data.statistic}}</div>

  </div>
  <div  class="d-flex flex-wrap justify-content-center">
  	<CardV2 v-for="(value , key) in data.statistic" :id=key :val=value :data="data.statistic" />
  </div>
</template>

<style></style>
