<template>

	<view class="content">

		<!-- 		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view> -->

		<view>
			<view style="background: #4CD964;width: 300rpx;color:#DD524D;" class="title" v-on:click="press()"></view>
			<label>hello uni-app!</label>
			<hr />
			<label>android手机测试!</label>
			<input type="text" class="text-area" value="请输入" v-model="inputText" @click="showInputText" />
			<br />
			<button @click="press" type="primary">按一按</button>
			<label>{{ title }}</label>
			<br />

			<label>计数器:{{ count }}</label>
			<hr />
			<button @click="home" type="primary">home</button>
			<br />
		</view>
		<br />
		<view>
			<h2>文章列表</h2>
			<br />
			<button type="primary" @click="loadArticles()">加载文章</button>
			<br />
			<table>
				<tr>
					<th>id</th>
					<th>title</th>
					<th>url</th>
					<th>summary</th>
					<th>author</th>
				</tr>
				<tr v-for="(item,index) in articleList">
					<td>{{ item.id }}</td>
					<td>{{ item.title }}</td>
					<td><a href="item.url">点击查看原文</a></td>
					<td>{{ item.summary }}</td>
					<td>{{ item.author }}</td>
				</tr>
			</table>
			<br />
		</view>

		<view>
			<h2>style测试</h2>
			<p class="important warning">
				这个类从哪个 jar 包加载的？为什么会报各种类相关的 Exception？

				我改的代码为什么没有执行到？难道是我没 commit？分支搞错了？

				遇到问题无法在线上 debug，难道只能通过加日志再重新发布吗？

				线上遇到某个用户的数据处理有问题，但线上同样无法 debug，线下无法重现！

				是否有一个全局视角来查看系统的运行状况？

				有什么办法可以监控到JVM的实时运行状态？

				怎么快速定位应用的热点，生成火焰图？
			</p>
			<hr />
			<p class="color_test">
				CSS 规则由两个主要的部分构成：选择器，以及一条或多条声明:
				每条声明由一个属性和一个值组成。
				属性（property）是您希望设置的样式属性（style attribute）。每个属性有一个值。属性和值被冒号分开。
			</p>
		</view>
		<hr />
		<view>
			<h2>图片测试</h2>
			<div>
				<p>图片测试</p>
			</div>
			<div class="img">
				<!-- <a> 标签的 target 属性规定在何处打开链接文档。 -->
				<a target="_blank" href="static/pic/0.jpg">图片</a>
				<!-- <img src="../../static/pic/0.jpg" alt="Ballade" width="160" height="160"> -->
				<img src="static/pic/0.jpg" alt="Ballade" width="160" height="160">
			</div> 

		</view>
		<hr />


	</view>

</template>

</view>
<script>
	var axios = require("../../static/libs/axios.js");
	export default {
		data() {
			return {
				title: 'Hello',
				count: 0,
				inputText: "",
				articleList: [],
			}
		},
		onLoad() {
			console.log("onLoad ... ");
		},
		methods: {
			press() {
				// console.log("按一按!");
				console.log('按钮!');
				this.title = "你好,uni-app!";
				this.count++;
			},
			home() {
				axios.get("http://10.222.100.10:8055/toutiao/home.json")
					.then(function(response) {
						console.log("response=", response);
					});
			},
			showInputText() {
				console.log("inputText=", this.inputText);
			},
			loadArticles() {

				var that = this;
				axios.get("http://10.222.100.10:8055/toutiao/load_test.json")
					.then(function(response) {
						console.log("response.data=", response.data);
						that.articleList = response.data.data;
					}).catch(function(error) {
						console.log("error=", error);
					});
			},
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}

	.important {
		font-weight: bold;
	}

	.warning {
		font-style: italic;
	}

	.important.warning {
		color: #F0AD4E;
		background-color: #DD524D;
	}

	.color_test {
		font-weight: bold;
		font-style: italic;
		color: #4CD964;
		background-color: #DD524D;
	}
</style>
