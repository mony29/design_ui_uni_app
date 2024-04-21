<template>
	<view style="margin: 20rpx;">
		<uni-forms ref="form" :modelValue="formData" :rules="rules">
			<uni-forms-item label="姓名" name="name">
				<uni-easyinput type="text" v-model="formData.name" placeholder="请输入姓名" />
			</uni-forms-item>
			
			<uni-forms-item label="性别" name="sex" class="myCheckbox">
				<view>
					<uni-data-checkbox v-model="formData.sex" :localdata="sex"></uni-data-checkbox>
				</view>
			</uni-forms-item>
			
			<uni-forms-item label="邮箱" name="email">
				<uni-easyinput v-model="formData.email" type="email" placeholder="请输入用户名"></uni-easyinput>
				<!-- <input class="input" v-model="formData.email" type="text" placeholder="请输入用户名" /> -->
			</uni-forms-item>
		</uni-forms>
		<button @click="submit">提交</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				// 表单数据
				formData: {
					name: '',
					sex: 0,
					phone: '',
					email: '',
				},
				sex: [{
					text: '男',
					value: 0
				}, {
					text: '女',
					value: 1
				}, {
					text: '未知',
					value: 2
				}],
				rules: {
					// 对name字段进行必填验证
					name: {
						rules: [{
								required: true,
								errorMessage: '请输入姓名',
							},
							{
								minLength: 2,
								maxLength: 5,
								errorMessage: '姓名长度在 {minLength} 到 {maxLength} 个字符',
							}
						]
					},
					// 对email字段进行必填验证
					email: {
						rules: [{
							required: true,
							format: 'email',
							errorMessage: '请输入正确的邮箱地址',
						}]
					}
				}
			}

		},
		methods: {
			// 触发提交表单
			submit() {
				let that = this
				this.$refs.form.validate().then(res => {
					console.log('表单数据信息：', res);
					console.log('表单数据信息：', that.formData);
				}).catch(err => {
					console.log('表单错误信息：', err);
				})
			}
		}
	}
</script>

<style>
	.myCheckbox {
		justify-content: center;
		display: flex;
		flex-direction: column;
	}
</style>