<template>
	<div id="home">
		<div class="grid-element" v-for="wdata in Wdata" :key="wdata.id"   >
			<router-link :to="{name: 'About' , params: { wdata }}"  class="r-link">
				<img class="img" v-bind:src="wdata.imgLink" />
				<h1>{{wdata.name}}</h1>
				<p>{{wdata.role}}</p>
			</router-link>
		</div>
	</div>	
</template>
<script>
	import Wdatas from './witcherdata.js';
	export default {
		name: 'Home',
		data(){
			return{
				Wdata : Wdatas
			}
		}
	}
</script>	
<style>
	#home{
			width: 80%;
			margin: 40px 10%;
			display: grid;
			grid-template-columns: 1fr 1fr 1fr;
			grid-column-gap: 20px;
			grid-row-gap:20px;
			font-family: monospace;
		}
		.grid-element{
			background:black;
			text-align: left;
			color: white;
		}
		.img{width: 100%}
		.grid-element h1{
			margin-top: 4px;margin-bottom: 0;padding-left: 20px;
		}
		.grid-element p{
			margin-top: 2px;
			color: gray;padding-left: 20px;
		}
		.grid-element:hover{
			transform: scale(1.2)
		}
		@media (max-width: 500px){
			#home{
				grid-template-columns: 1fr;
			}
		}
</style>