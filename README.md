#  Cross Platform IDE - HBuilderX(uni-app)

| Name           | Xu Yiming  |
| -------------- | ---------- |
| Student Number | 3035775769 |

[toc]

## [HBuilder](https://www.dcloud.io/hbuilderx.html)

HBuilder, H is short for HTML and Builder is the builder.

It is a generic IDE, or editor, for front-end developers. It is similar to vscode, sublime and webstorm.

It can develop normal web projects, but also uni-app projects, 5+App projects, wap2app projects produced by DCloud.

Its advantages over competing products are.

​	· Runs faster (c++ kernel)
​	· Much better support for markdown and vue
​	· It can also develop apps and applets, especially good support for DCloud's uni-app, 5+App and other mobile end products

<img src="https://hku-1259018500.cos.ap-hongkong.myqcloud.com/app/app-picimage-20210426161418572.png" alt="image-20210426161418572" style="zoom: 50%;" />

## [Uniapp](https://uniapp.dcloud.io/)

**uni-app**, uni means unified, aggregated. Although the name has app in it, it actually refers to front-end applications in general.

uni-app is an all-end development framework for js developers that can be developed once compiled for web, app, applet (WeChat/AliPay/Baidu/ByteDance/QQ), and fast apps.

It supports the use of a variety of ide development, such as vscode, webstorm, but used in combination with HBuilderX more perfect.

uni-app is a vuejs syntax + API for applets, it has a standalone js engine and the native capabilities are extended based on the standalone js engine rather than the webview based extension solution.

On the app side, uni-app supports native rendering for the view layer (similar to react native at this point) and also supports rendering using webview (similar to the applet engine at this point), the choice is up to the developer.

![表格  描述已自动生成](https://hku-1259018500.cos.ap-hongkong.myqcloud.com/app/app-picclip_image002.gif)

[^1]: Figure 1 Uniapp Framework

![image-20210426165128229](https://hku-1259018500.cos.ap-hongkong.myqcloud.com/app/app-picimage-20210426165128229.png)

[^2]: Figure 2 Cross Platform Deployment

### Quick Experience

It's not a dream to code once and deploy to 10 platforms in one set. Seeing is believing. Scan the 10 QR codes and experience the most comprehensive cross-platform results!

<img src="https://hku-1259018500.cos.ap-hongkong.myqcloud.com/app/app-picimage-20210426161258830.png" alt="image-20210426161258830" style="zoom: 80%;" />

## Installation

### Download

You can download the HbuilderX IDE from this website (https://www.dcloud.io/hbuilderx.html), as you need to do development tasks, so choose the App Development version (including the Windows version/MacOS version)

<img src="https://hku-1259018500.cos.ap-hongkong.myqcloud.com/app/app-picimage-20210426160506353.png" alt="image-20210426160506353" style="zoom: 50%;" />

### Installation

The Windows version is downloaded as a zip package. After extracting the zip package to a directory, double click on the exe file to complete the installation of the IDE and open the software.
The Mac version is a DMG file that can be downloaded and installed by dragging the app into the application folder.

After completing the installation, you can configure the theme of the IDE and view an introduction to the relevant IDE and syntax.

<img src="https://hku-1259018500.cos.ap-hongkong.myqcloud.com/app/app-picimage-20210426162458716.png" alt="image-20210426162458716" style="zoom: 33%;" />

## Develop The First Demo

Demo: 

​	A user can enter 3 numbers and there is a button on the same user interface. 

​	Upon the button is clicked, the sum of the 3 numbers will be calculated and the result will be displayed on the same user interface

### Create a project and run the app on machine

Click on New in the top left corner, select the project and create a new uniapp project.

<img src="https://hku-1259018500.cos.ap-hongkong.myqcloud.com/app/app-picimage-20210426170231916.png" alt="image-20210426170231916" style="zoom: 67%;" />

<img src="https://hku-1259018500.cos.ap-hongkong.myqcloud.com/app/app-picimage-20210426170452606.png" alt="image-20210426170452606" style="zoom: 50%;" />

At this point, the project was successfully created. The directory for this project is in the left-hand column of the IDE and the right-hand column is the editing area for the code.

<img src="https://hku-1259018500.cos.ap-hongkong.myqcloud.com/app/app-picimage-20210426170600645.png" alt="image-20210426170600645" style="zoom: 50%;" />

For real-machine testing, we can also compile the code to an Android emulator. Here we use the NetEase [MuMu emulator](http://mumu.163.com/) as an example. After downloading and installing the MuMu emulator, get the adb port of the emulator (7555) and modify the parameter of the Android emulator port in Settings.json to 7555, HBudilerX will automatically detect the emulator and prompt MuMu is connected to HBuilderX editor. At this point, we can click Run to Android (MuMu) to finish running the app on this emulator.

<img src="https://hku-1259018500.cos.ap-hongkong.myqcloud.com/app/app-picimage-20210426173906619.png" alt="image-20210426173906619" style="zoom:67%;" />

## Write The Code

In vue.js-based uniapp, the main code of a functional page can be divided into three parts: 1. template, which is responsible for the content of the display layer 2. script, which is responsible for the logic calculation part 3. style, which is responsible for adjusting the style.
The code for the implementation of this project is shown below in the three parts mentioned above.

### template

First, add the required header "Number Input" and three text input boxes in numeric form to the template, together with the displayed "result" and the submit calculation button "Submit".

```vue
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
```

<img src="https://hku-1259018500.cos.ap-hongkong.myqcloud.com/app/app-picimage-20210427161533710.png" alt="image-20210427161533710" style="zoom: 67%;" />

### script

Next, in the script area, set the data required for this page: input1-3 and result, and in method, write the assignment to be made when the input action is listened to. You also need to write the summation operation that will be performed when the sumbit button is clicked.

```javascript
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
```

### style

Finally, in the sytle area, trim the style of the display by writing css content.

```css
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

```

Once we have finished writing the code, click Run and run it on the device, then the app will be automatically installed on the device and opened to experience the full functionality.

<img src="https://hku-1259018500.cos.ap-hongkong.myqcloud.com/app/app-picimage-20210427162103632.png" alt="image-20210427162103632" style="zoom: 67%;" /><img src="https://hku-1259018500.cos.ap-hongkong.myqcloud.com/app/app-picimage-20210427162133413.png" alt="image-20210427162133413" style="zoom: 67%;" />

