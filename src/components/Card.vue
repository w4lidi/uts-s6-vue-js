<script>
	export default{
		data(){
			return{
				
			}
		},
		props:[
				"logopath","clubname"
			],
		emits:[
			'ViewDetails']
	}
</script>


<template>
	<div class="card border-0 m-1" @click="$emit('ViewDetails')" style="width: 10rem;">
		<img :src="logopath" class="card-img-top" alt="logo">
	  	<div class="card-body">
	    	<h6 class="text-center">{{clubname}}</h6>
	  	</div>
	</div>
</template>


<style>
	img{
		
	}
</style>