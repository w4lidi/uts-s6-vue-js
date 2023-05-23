<script>
	export default{
		data(){
			return{
				
			}
		},
		props:[
			"id","val"
			],
	}
</script>

<template>
	
	<div class="card  border-0" style="width: 7rem;">
  		<div class="card-body">
    		<h1 class="card-title text-center">{{val}}</h1>
    		<p class="card-subtitle text-uppercase fw-bold text-center text-body-secondary">
    			<span v-if="id == 'red card'"><img src=../assets/img/liga1/card/red.png width=15></span>
    			<span v-if="id == 'yellow card'"><img src=../assets/img/liga1/card/yellow.png width=15></span>{{id}}
    		</p>
  		</div>
	</div>
</template>

<style></style>