<template>
    <div id="cesiumContainer">
      
    </div>
  </template>
  
  <script setup>
  
  import { onMounted } from 'vue'
  import * as Cesium from 'cesium'
  onMounted(()=>{
    Cesium.Ion.defaultAccessToken = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJqdGkiOiI1NDYxYjhlNC03ZGQ4LTRkY2EtOTZkZi04MDVmMWIxZjcwNGIiLCJpZCI6MTc5NzM5LCJpYXQiOjE3MDA1NTk3Nzh9.6TOPr97qzfQRDzRf6Zv8ecLPgs1FGnIw_Wiq4JuC0dY'
  
    //viewer是所有API的开始
    const viewer = new Cesium.Viewer('cesiumContainer',{
      timeline: false,//时间轴控件
      animation: false,//动画控件
      geocoder: false,//搜索按钮
      homeButton: false,//主页控件
      sceneModePicker: false,//投影方式按钮 
      baseLayerPicker: false,//图层选择按钮
      navigationHelpButton: false,//帮助手势按钮
    })
  })
  </script>
  
  <style>
  #cesiumContainer {
    width: 100vw;
    height: 100vh;
    overflow: hidden;
  }
  
  .cesium-viewer-botton{
    display: none;
  }
  
  </style>
  