<template>
	<div id="About">
		<div class="about-flex-left">
			<img v-bind:src="wdata.imgLink" class="img"/>
		</div>
		<div class="about-flex-right">
			<div class="about-flex-right-content">
				<h1>{{name}}</h1>
				<h2>{{role}}</h2>
			</div>
		</div>
	</div>
</template>
<script>
export default {
  name: 'About',
  props: ['wdata'],
  data(){
	  return{
		imgLink: '',
	 	name: '',
	    role: ''
	  }
  },
  mounted(){
	  if(this.wdata){
		this.imgLink = this.wdata.imgLink
		this.name = this.wdata.name 
	  	this.role = this.wdata.role
	  }
  }
}
</script>
<style>
	#About{
		display: flex;
		width:80%;
		margin: 60px 10%;
		color: white;
	}
	.about-flex-left{
		width:50%;
	}
	.about-flex-right{
		width: 50%;
		background-color:black;
		display: grid;
		align-items: center;
		text-align: left;
	}
	.about-flex-right h1{font-size: 60px;}
	.about-flex-right h2{font-size: 42px;color: gray;margin-top: -40px;}
	.about-flex-right-content{
		margin-left: 20px;
	}
	@media (max-width:500px){
		#About h1{font-size: 30px;}
		#About h2{font-size: 24px;margin-top: -20px;}
		#About{display: block;}
		.about-flex-right , .about-flex-left{width: 100%;}
	}
</style>