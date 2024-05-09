<template>
	<view>
		<uni-section class="mb-10" title="基本信息" type="line">
			<view class="uni-flex uni-row row">
				<view class="text" style="width: 200rpx;">姓名：</view>
				<view class="text" style="-webkit-flex: 1; flex: 1;">
					<input class="uni-input" focus placeholder="自动获得焦点" v-model="name" />
				</view>
			</view>
			<view class="uni-flex uni-row row">
				<view class="text" style="width: 200rpx;">性别：</view>
				<view class="text" style="-webkit-flex: 1; flex: 1;">
					<radio-group @change="radioChange">
						<radio value="1" checked="true">男</radio>
						<radio value="2" checked="false">女</radio>
					</radio-group>
				</view>
			</view>
			<view class="uni-flex uni-row row">
				<view class="text" style="width: 200rpx;">出生日期：</view>
				<view class="text" style="-webkit-flex: 1; flex: 1;">
					<picker mode="date" :value="birthDate" :start="startDate" :end="endDate">
						<view class="uni-input">{{birthDate}}</view>
					</picker>
				</view>
			</view>

			<view class="uni-flex uni-row row">
				<view class="text" style="width: 600rpx;">报名</view>
				<view class="text" style="-webkit-flex: 1; flex: 1;">
					<switch @change="switchChange" />
				</view>
			</view>
		</uni-section>

		<uni-section class="mb-10" title="报名信息" type="line" style="margin-top: 10rpx;" v-if="show">
			<view class="uni-flex uni-row row">
				<view class="text" style="width: 200rpx;">地址：</view>
				<view class="text" style="-webkit-flex: 1; flex: 1;">
					<input class="uni-input" focus placeholder="输入家庭地址" v-model="address" />
				</view>
			</view>
			<view class="uni-flex uni-row row">
				<view class="text" style="width: 200rpx;">城市：</view>
				<view class="text" style="-webkit-flex: 1; flex: 1;">
					<picker @change="bindPickerChange" :value="index" :range="city" :range-key="name">
						<view class="uni-input">{{city[index].name}}</view>
					</picker>
					<text v-model="selectedCity">{{selectedCity}}</text>
				</view>
			</view>

			<view>
				<view>选择课程</view>
				<view>
					<checkbox-group @change="bindCourseChange">
						<view v-for="(course, index) in courseList">
							<checkbox :value="index" />{{course.name}}
						</view>
					</checkbox-group>
				</view>
			</view>
		</uni-section>


		<view>
			<button @click="myButtonClick()">提交</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				birthDate: "2020-04-20",
				startDate: "2024-04-20",
				endDate: "2004-04-23",
				name: "乔莫尼",
				address: "大理大学",
				city: [{
					name: '大理'
				}, {
					name: '下关'
				}, {
					name: '丽江'
				}],
				index: 0,
				show: false,
				courseList: [{
					'id': '1',
					'name': 'Java程序设计',
					'checked': 'true'
				}, {
					'id': '2',
					'name': '数据结果'
				}, {
					'id': '3',
					'name': '机器学习'
				}],
				courseSelectedIndex: '',
				sex: 1,
			}
		},
		methods: {
			myButtonClick() {
				// let sexValue = this.sex === 1 ? "男":"女";
				let message = "姓名：" + this.name + "，出生日期：" + this.birthDate + "，性别：" + this.sex + "，地址：" + this.address +
					"，选择课程：";
				for (let i = 0; i < this.courseSelectedIndex.length; i++) {
					let index = this.courseSelectedIndex[i];
					let courseName = this.courseList[index].name;
					message = message + courseName + "，"
				}
				const selectedCityName = this.city[this.index].name;
				message += "城市：" + selectedCityName;
				uni.showToast({
					title: message,
					icon: 'none'
				})
			},

			radioChange: function(e) {
				console.log(e.detail.value);
				this.sex = e.detail.value;
			},

			switchChange: function(e) {
				this.show = e.detail.value;
			},

			bindPickerChange: function(e) {
				this.index = e.detail.value;
				const selectedCity = this.city[this.index].name;
				console.log("Selected City : ", selectedCity);

			},

			bindCourseChange: function(e) {
				console.log(e.detail.value);
				this.courseSelectedIndex = e.detail.value;
			},
		}
	}
</script>

<style>
	body {
		background-color: #EAECEE;
	}

	.uni-list-cell {
		display: flex;
		justify-content: flex-start
	}

	.uni-flex {
		display: flex;
		margin-top: 20rpx;
		margin-bottom: 20rpx;
	}

	.mb-10 {
		margin-top: 10rpx;
		padding: 10rpx;
		margin-bottom: 20rpx;
	}

	button {
		background-color: royalblue;
		color: white;
	}

	.text {
		font-size: 32rpx;
	}
</style>