<template>
	<view>
		<view v-for="(item, index) in students">
			<view class="persons">{{index}} - {{item.name}} - {{item.age}}</view>
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
</script>

<style>

</style>