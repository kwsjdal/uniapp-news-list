<template>
	<view class='container'>
		<view class="title">
			{{title}}
		</view>
		<view class="" v-html='content'>
			
		</view>
	</view>
</template>

<script setup>
	import {ref} from 'vue'
	const title=ref('')
	const content=ref('')
	import {onLoad} from '@dcloudio/uni-app'
	onLoad((ops)=>{
		
		uni.request({
			url:'http://unidemo.dcloud.net.cn/api/news/36kr/'+ops.id,
			method:'GET',
			data:{},
			success:res=> {
				console.log(res)
				title.value=res.data.title;
				content.value=res.data.content;
				
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
		 .title{
			 font-size:1.5rem;
			 font-weight: 700;
			 line-height: 2em;
		 }
</style>
