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
    })
  
    //经纬度转笛卡尔坐标，返回的是一个笛卡尔坐标(z!=高度)
    const cartesian = Cesium.Cartesian3.fromDegrees(110,20,20)//经度，纬度，高度
    console.log(cartesian)
  
    //笛卡尔坐标转经纬度
    //1.笛卡尔转弧度坐标
    let cartographic = Cesium.Cartographic.fromDegrees(cartesian)
    console.log(cartographic)
    //2.弧度坐标转角度坐标
    let lon = Cesium.Math.toDegrees(cartesian.longitude)
    let lat = Cesium.Math.toDegrees(cartesian.latitude)
    // let lon = 180 / Math.PI * cartographic.longitude （不准确，精度问题）
    // let lat = 180 / Math.PI * cartographic.latitude
    console.log(lon,lat,cartesian.height)
    // 0.1+0.2 != 0.3 js小数位精度问题
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
  