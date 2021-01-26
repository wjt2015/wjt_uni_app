<template>
	<view>
		<h2>view组件测试</h2>
		<view class="title" hover-class="hover-title" hover-start-time="1000" hover-stay-time="2000">
			hello world!
		</view>
	</view>
</template>
<script>
	export default {
		data() {
			return {

			}
		},
		methods: {

		}
	}
</script>

<style>
	.title {
		width: 100%;
		text-align: center;
		background-color: #333333;
		color: #F0AD4E;
	}

	.hover-title {
		font-size: 30px;
		color: #DD524D;
	}
</style>
