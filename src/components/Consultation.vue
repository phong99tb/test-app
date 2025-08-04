<template>
  <div style="position: relative; overflow: hidden;">
    <div :style="computedStyle" class="over_img">
      <div style="position: relative; z-index: 1; color: white; display: flex; flex-direction: column; gap: 10px;">
        <p>{{ title }}</p>
        <p>{{ time }}</p>
      </div>
    </div>
    <div style="position: absolute; inset: 0; background-color: rgba(0,0,0,0.7); z-index: 0; border-radius: 10px;"></div>
  </div>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  title: String,
  time: String,
  bg: String,
})

const computedStyle = computed(() => ({
  position: 'relative',
  backgroundImage: `url(${props.bg})`,
  backgroundSize: 'cover',
  backgroundPosition: 'center',
  boxShadow: '0px 2px 10px 0px #000000B2',
  borderRadius: '10px',
}))
</script>

<style scoped>
.over_img {
  height: 150px !important;
  display: flex;
  flex-direction: column;
  border-radius: 10px;
  align-items: center;
  text-align: center;
  justify-content: center;
}
</style>
