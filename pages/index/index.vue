<template>
	<view class="container">
		<uni-list>
			<uni-list-item v-for='item of news'
			 :title='item.title' 
			 :note='item.author_name'
			 :thumb="item.cover" thumb-size="lg" link="navigateTo"
			 :to="'../detail/detail?id='+item.post_id"></uni-list-item>
		</uni-list>
	</view>
</template>

<script setup>
	import{ref} from 'vue'
	import {onLoad} from '@dcloudio/uni-app'
	const news=ref([])
	
	onLoad(()=>{
		uni.request({
			url:'http://unidemo.dcloud.net.cn/api/news',
			method:'GET',
			data:{},
			success:res=> {
				news.value=res.data;
				
			}
		})
	})
</script>

<style>
	.container {
		padding: 20px;
		font-size: 14px;
		line-height: 24px;
	}
</style>
