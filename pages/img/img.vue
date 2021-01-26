<template>
	<view>
		
		<button type="primary" class="content" hover-class=""><h2>按一按</h2></button>
		<hr/>
		<view>
			<map style="width: 100%;height:600px;" :latitude="latitude" :longitude="longitude" :marker="covers" enable-3D="true" show-compass="true"
			 
			 enable-location="true">
				腾讯地图
			</map>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				id:0,
				latitude:38.9,
				longitude:116.9,
				covers:[{
					latitude:55.09,
					longitude:116.92,
					iconPath:"/static/pic/0.jpg"
				},{
					latitude:62.92,
					longitude:115.099,
					iconPath:"/static/pic/1.jpg"
				}]
			}
		},
		methods: {
			
		}
	}
</script>

<style>

</style>
