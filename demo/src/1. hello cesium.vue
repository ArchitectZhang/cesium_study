<template>
    <div id="cesiumContainer">
      
    </div>
  </template>
  
  <script setup>
  
  import { onMounted } from 'vue'
  import * as Cesium from 'cesium'
  onMounted(()=>{
    Cesium.Ion.defaultAccessToken = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJqdGkiOiI1NDYxYjhlNC03ZGQ4LTRkY2EtOTZkZi04MDVmMWIxZjcwNGIiLCJpZCI6MTc5NzM5LCJpYXQiOjE3MDA1NTk3Nzh9.6TOPr97qzfQRDzRf6Zv8ecLPgs1FGnIw_Wiq4JuC0dY'
    
    //ArcGIS影像图层
    const esri =  new Cesium.ArcGisMapServerImageryProvider({
      url:"https://services.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapSever1",
      enablePickFeatures: false,
    });
  
    //viewer是所有API的开始
    const viewer = new Cesium.Viewer('cesiumContainer',{
      imageryProvider: esri, //自定义图层，默认谷歌的影像图层
      terrainProvider: Cesium.createWorldTerrain({
        // requestWaterMask: true,//水面特效
      }) //创建地形图层
    })
  })
  </script>
  
  <style scoped>
  #cesiumContainer {
    width: 100vw;
    height: 100vh;
    overflow: hidden;
  }
  
  </style>
  