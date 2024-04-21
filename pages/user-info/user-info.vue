<template>
	<view>
		<uni-section class="mb-10" title="基本信息" type="line">
			<view class="uni-flex uni-row row">
				<view class="text" style="width: 200rpx;">姓名</view>
				<view class="text" style="-webkit-flex: 1; flex: 1;">
					<input class="uni-input" focus placeholder="自动获得焦点" v-model="name" />
				</view>
			</view>
			<view class="uni-flex uni-row row">
				<view class="text" style="width: 200rpx;">性别</view>
				<view class="text" style="-webkit-flex: 1; flex: 1;">
					<radio-group @change="radioChange">
						<radio value="1" checked="true">男</radio>
						<radio value="2" checked="false">女</radio>
					</radio-group>
				</view>
			</view>
			<view class="uni-flex uni-row row">
				<view class="text" style="width: 200rpx;">出生日期</view>
				<view class="text" style="-webkit-flex: 1; flex: 1;">
					<picker mode="date" :value="date" :start="startDate" :end="endDate">
						<view class="uni-input">{{date}}</view>
					</picker>
				</view>
			</view>

			<view class="uni-flex uni-row row">
				<view class="text" style="width: 200rpx;">Register</view>
				<view class="text" style="-webkit-flex: 1; flex: 1;">
					<switch @change="switchChange" />
				</view>
			</view>
		</uni-section>

		<uni-section class="mb-10" title="报名信息" type="line" style="margin-top: 10rpx;" v-if="show">
			<view class="uni-flex uni-row row">
				<view class="text" style="width: 200rpx;">地址</view>
				<view class="text" style="-webkit-flex: 1; flex: 1;">
					<input class="uni-input" focus placeholder="输入家庭地址" v-model="address" />
				</view>
			</view>
			<view class="uni-flex uni-row row">
				<view class="text" style="width: 200rpx;">城市</view>
				<view class="text" style="-webkit-flex: 1; flex: 1;">
					<picker @change="bindPickerChange" :value="index" :range="array" :range-key="name">
						<view class="uni-input">{{array[index].name}}</view>
					</picker>
				</view>
			</view>
		</uni-section>

		<view>
			<button @click="myButtonClick()">Submit</button>
		</view>
	</view>
</template>
<script>
	export default {
		data() {
			return {
				date: "2024-04-20",
				startDate: "2024-04-20",
				endDate: "2004-04-23",
				name: "mony",
				address: "",
				array: [{
					name: '大理'
				}, {
					name: '下关'
				}, {
					name: '丽江'
				}],
				index: 0,
				show: false,
			}
		},
		methods: {
			myButtonClick() {
				uni.showToast({
					title: this.name,
					icon: 'none'
				})
			},
			radioChange: function(e) {
				// console.log(e.detail);
				// console.log('radio changing', e.detail.value);
			},
			switchChange: function(e) {
				this.show = e.detail.value
				// console.log(e);
				// console.log("Swich", e.detail.value);
				// console.log('switch changing', e.datail.value);
			},
			bindPickerChange: function(e){
				// console.log("Pick");
				// console.log("Picker", e);
				// console.log('picker changing'+ e.detail.value);
				// this.index = e.detail.value;
			}
			
		}
	}
</script>

<style>

</style>


<!-- <template>
	<view>
		<view v-for="(item, index) in students">
			<view class="persons">{{index}} - Name :{{item.name}} - Age:{{item.age}}</view>
		</view>
		<view v-if="show">
			这里是条件展示的内容....
		</view>
	</view>
</template>
<script>
	export default {
		data() {
			return {
				students: [{
						name: "张三",
						age: 18
					},
					{
						name: "李四",
						age: 20
					}
				],
				show:false
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script> -->