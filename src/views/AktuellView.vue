<script lang="ts" setup>
import { computed } from 'vue'
import SlideShow from '../components/SlideShow.vue'

const awsUrl = 'https://klarenthal.s3.eu-north-1.amazonaws.com/homeSlides/'
const slides = ['football1.jpg', 'football2.jpg', 'football3.png', 'football4.jpg']

const src = computed(() => {
  const arr = []
  for (let slide of slides) {
    arr.push(awsUrl + slide)
  }
  return arr
})
</script>

<!---- Html ---------------------------------------------------->

<template>
  <div class="text">Aktuell</div>
  <!-- <SlideShow height="400px" autorun :slides="src" /> -->
  <div class="parent w-full p-2">
    <img
      class=""
      src="https://klarenthal.s3.eu-north-1.amazonaws.com/Aktuelles/aktuel.png"
      alt=""
    />
  </div>
</template>

<!---- Style ---------------------------------------------------->

<style lang="scss" scoped>
.text {
  text-align: center;
  font-size: 40px;
  padding: 20px;
  font-weight: bold;
}

.parent {
  display: flex;
  align-items: center;
  justify-content: center;

  img {
    max-width: 500px;
    width: 100%;
  }
}
</style>
