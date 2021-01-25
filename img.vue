<template>

	<view>
		<h2>图片测试</h2>
		<view>
			<p>图片测试</p>
		</view>

		<view class="img">
			<!-- <a> 标签的 target 属性规定在何处打开链接文档。 -->
			<a target="_blank" href="static/pic/0.jpg">图片</a>
			<!-- <img src="../../static/pic/0.jpg" alt="Ballade" width="160" height="160"> -->
			<img src="static/pic/0.jpg" alt="Ballade" width="160" height="160">
			<img src="../../static/pic/0.jpg" alt="Ballade" width="160" height="160">
		</view>
		
		<hr/>
		<view>
			<h2>{{articleTitle}}</h2>
		</view>
		
		<hr/>
		<hr/>
		

	</view>

</template>

<script>
	var axios = require("../../static/libs/axios.js");
	
	export default {
		data() {
			return {
				uid:1,
				articleId:1,
			}
		},
		methods: {

		},
		computed:{
			// 计算属性;
			articleTitle:function(){
				axios.get("http://10.222.100.10:8055/toutiao/artitleTitle.json?uid="+this.uid+"&articleId="+this.articleId)
				.then(function(response){
					console.log("response.data=",response.data);
					this.articleTitle=response.data;
				})
				.catch(function(error){
					console.log("response error!error=",error);
				});
			}
		}
	}
</script>

<style>


</style>
