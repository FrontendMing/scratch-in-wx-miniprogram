# 微信小程序 刮刮乐 圆形区域清除

## 思路
1、将背景直接用图片img.定位在canvas的下边；
2、在canvas上绘制刮的灰色涂层；
3、通过绑定的事件，清除对应区域的涂层；
4、判断涂层清除区域是否超过设置的可见百分比，如果超过则全部涂层清除，否则不清除。

## wxml
## @example
<view>
  <image src='图片地址'></image>
  <canvas style='width: 350px;height: 350px;' 
          canvas-id='canvas-demo' 
          bindtouchstart="touchStart" 
          bindtouchmove="touchMove" 
          bindtouchend="touchEnd"></canvas>
</view>

## js
## 导入文件
import Scratch from '../../utils/scratch.js'

## 在页面 onLoad 时实例化
## @example
onLoad: function(options){
  new Scratch(this,{
    canvasId: 'canvas-demo'
  })
} 