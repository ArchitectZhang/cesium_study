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
  const viewer = new Cesium.Viewer('cesiumContainer',{})

  const position = new Cesium.Cartesian3.fromDegrees(110,20,300000)
  viewer.camera.setView({
    destination: position,
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
