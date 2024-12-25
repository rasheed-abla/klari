<script lang="ts" setup>
import SamIcon from './SamIcon.vue'
import { onMounted, ref } from 'vue'
import { gsap } from 'gsap'
import { useRouter } from 'vue-router'

const infoList = ref([
  {
    id: 'A1',
    name: 'A-Jugend'
  },
  {
    id: 'B1',
    name: 'B-Jugend'
  },
  {
    id: 'C1',
    name: 'C-Jugend'
  },
  {
    id: 'D1',
    name: 'D1-Jugend'
  },
  {
    id: 'D2',
    name: 'D2-Jugend'
  },
  {
    id: 'D3',
    name: 'D3-Jugend'
  },
  {
    id: 'D4',
    name: 'D4-Jugend'
  },
  {
    id: 'D5',
    name: 'D5-Jugend'
  },
  {
    id: 'E1',
    name: 'E1-Jugend'
  },
  {
    id: 'E2',
    name: 'E2-Jugend'
  },
  {
    id: 'E3',
    name: 'E3-Jugend'
  },
  {
    id: 'F1',
    name: 'F1-Jugend'
  },
  {
    id: 'F2',
    name: 'F2-Jugend'
  },
  {
    id: 'G1',
    name: 'G1-Jugend'
  },
  {
    id: 'G2',
    name: 'G2-Jugend'
  },
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
  <div ref="MenuItems" class="wrapper_1">
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
.wrapper_1 {
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
