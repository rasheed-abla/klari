<script lang="ts" setup>
import SamIcon from './SamIcon.vue'
import { onMounted, ref } from 'vue'
import { gsap } from 'gsap'
import { useRouter } from 'vue-router'

const infoList = ref([
  {
    id: '2M',
    name: '2.Mannschaft'
  }
])

const emit = defineEmits(['close', 'closeAll'])
const MenuItems = ref<HTMLElement | null>(null)
const router = useRouter()

onMounted(() => {
  if (MenuItems.value) {
    gsap.fromTo(MenuItems.value, { scale: 0 }, { scale: 1, duration: 0.3, ease: 'power1.inOut' })
  }
})

function emitClose() {
  emit('close')
}

function emitCloseAll() {
  emit('closeAll')
}

function close() {
  gsap.to(MenuItems.value, {
    scale: 0,
    duration: 0.3,
    ease: 'power1.inOut',
    onComplete: emitClose
  })
}

function navigate(id: String) {
  router.push(`/team/${id}`)
  emitClose()
  emitCloseAll()
}
</script>

<!---- Html ---------------------------------------------------->

<template>
  <div ref="MenuItems" class="wrapper_2">
    <div @click="close()" class="close">
      <SamIcon color="ffffff">material-symbols:arrow-left-alt-rounded</SamIcon>
    </div>
    <div @click="navigate(item.id)" v-for="item in infoList" :key="item.id" class="item">
      {{ item.name }}
    </div>
  </div>
</template>

<!---- Style ---------------------------------------------------->

<style lang="scss" scoped>
.wrapper_2 {
  padding-top: 60px;
  background-image: linear-gradient(#858181, #f8f8f6) !important;
  color: #ffffff !important;
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: 11;
  .close {
    position: absolute;
    top: 30px;
    left: 30px;
  }
}

.item {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 3px;
}
</style>
