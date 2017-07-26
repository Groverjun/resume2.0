<template>	
	<div class="resume-wrap">
	 	<pre v-html="data"></pre>
	</div>
</template>

<script>
	export default {
	props:["data01"],
	  data () {
	    return{
	    	msg:"shah"
	    }
	  },
	  computed: {	
		data(){
			return this.data01
		}
	  
	  }
	}
</script>

