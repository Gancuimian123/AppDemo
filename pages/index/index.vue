<template>
	<view class="content">
		<view class="uni-form-item uni-column">
			<view style="margin-top: 100upx; font-size: 50upx;">Number Input</view>
			<view class="uni-form-item uni-column">
				<input class="uni-input" style="border: 1px solid #000000; margin-top: 10upx;" type="number" @input="OnKeyInput1" placeholder="Input the first number here" />
				<input class="uni-input" style="border: 1px solid #000000; margin-top: 10upx;" type="number" @input="OnKeyInput2" placeholder="Input the second number here" />
				<input class="uni-input" style="border: 1px solid #000000; margin-top: 10upx;" type="number" @input="OnKeyInput3" placeholder="Input the third number here" />
			</view>
			
			<button style="margin-top: 30upx;" type="primary" @click="CalSum()">Submit</button>
			
			<view style="margin-top: 100upx; font-size: 50upx;">Result：{{result}}</view>
			
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				input1: 0,
				input2: 0,
				input3: 0,
				result: 0
			}
		},
		onLoad() {

		},
		methods: {
			OnKeyInput1: function(event){
				this.input1 = parseInt(event.target.value) 
			},
			OnKeyInput2: function(event){
				this.input2 = parseInt(event.target.value) 
			},
			OnKeyInput3: function(event){
				this.input3 = parseInt(event.target.value) 
			},
			CalSum: function(){
				this.result = this.input1+this.input2+this.input3
			}
			
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

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
