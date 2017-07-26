<template>
	<div class="styles-wrap" id="box">
		<div >
			<pre v-html="html1"></pre>
			<pre v-html="html2"></pre>
		</div>

		<div v-html="css1"></div>
	</div>
</template>
<script>
import Prism from 'prismjs'/*语法高亮的模块*/
export default { 
		props:["css01","css02"],
		computed: {	//Vue检测到数据发生变动时就会执行对相应数据有引用的函数。		
			css1(){
				return '<style>' + this.css01+ '</style>'
			},
			html1(){
				return Prism.highlight(this.css01, Prism.languages.css)
			},
			html2(){
				return this.css02
			}
			
		}
	}
</script>