  <template>
    <div class="spline-container">
      <spline-viewer
       url="https://prod.spline.design/aHuYkNcf1ob8rmmu/scene.splinecode">
      </spline-viewer>
    </div>
  </template>

<script setup>
import { onMounted, ref } from 'vue'

const splineContainer = ref(null)

onMounted(async () => {
  if (process.client) {
    await import('https://unpkg.com/@splinetool/viewer@1.9.76/build/spline-viewer.js')
  }
})
</script>

<style scoped>
.spline-container {
  position: fixed; /* Occupa tutta la finestra */
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
}

spline-viewer {
  width: 100%;
  height: 100%;
}
</style>