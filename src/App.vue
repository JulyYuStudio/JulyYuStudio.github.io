<script setup>
import * as THREE from 'three'
import FOG from 'vanta/dist/vanta.fog.min'
import { ref, onMounted, onBeforeUnmount, nextTick } from 'vue';

  const vantaRef = ref(null);
  const vantaEffect = ref(null);

  onMounted(() => {
    nextTick(() => {
      vantaEffect.value = FOG({
        el: vantaRef.value,
        THREE: THREE
      })
    })
  });

  onBeforeUnmount(() => {
    if (vantaEffect.value) {
      vantaEffect.value.destroy()
    }
  });

</script>

<template>
  <div class="app-background" ref="vantaRef"/>
    
  <div class="app-fullscreen">
      <router-view />
    </div>
</template>

<style scoped>


.app-background {
  margin: 0;
  display: flex;
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  z-index: -1;
}

.app-fullscreen {
  min-height: 100vh;
  height: 100vh;
  box-sizing: border-box;
  position: relative;
  z-index: 1;
  display: flex;
  justify-content: center;
}
</style>
