<template>
	<div id="app">
		<csstxt :css01="css01" :css02="css02"></csstxt>
		<datatxt :data01="data01"></datatxt>
	</div>
</template>
<script>
import csstxt from  "./component/Style.vue";//引入csstxt组件
import datatxt from  "./component/resume.vue";//引入datatxt组件
import styles from './data/style';//引入写好的说明文件
import datas from './data/data';//引入写好的简历文件
import marked from 'marked'/*引入maked.js*/
export default {
  name: 'app',
  components:{csstxt,datatxt},
  data () {
    return {
        css1:styles[0],
        css01:``,
        data1:datas,
        data01:``,
        css2:styles[1],
        css02:``
        
    }
  },
  created() {//当元素放到页面里要做的事
 		let n=0;
 		let s=0;
 		let n2=0
 		let css1=setInterval(()=>{
 			n=n+1;
 			if(n==this.css1.length){
 				clearInterval(css1)
 				//第一步完成
 				let data1=setInterval(()=>{
 					s=s+1;
 					if(s==this.data1.length){
 						clearInterval(data1)
 						//  第二步完成    
		 				let css2=setInterval(()=>{
		 					n2=n2+1;
		 					if(n2==this.data1.length){
		 						clearInterval(css2);
		 						this.data01=marked(this.data01)
		 					}
		 					this.css02=this.css2.substring(0,n2)
		 				},100)
		 				
		 				//            
 					}
 					this.data01=this.data1.substring(0,s)
 				},100)
 				
 				
 			}
 			this.css01=this.css1.substring(0,n)
 		},100)
  
  
  
  }
}
</script>
