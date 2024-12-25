<script lang="ts" setup>
import useTeams from '../composables/teams'
import JugendWidget from '@/components/JugendWidget.vue'

const teams = useTeams().allTeams
</script>

<!---- Html ---------------------------------------------------->

<template>
  <section class="flex md:flex-row flex-col justify-center items-center md:justify-around my-5">
    <JugendWidget class="w-[190px]" id="A1" :team="teams['A1']" />
    <JugendWidget id="B1" :team="teams['B1']" />
    <JugendWidget id="C1" :team="teams['C1']" />
    <JugendWidget id="D1" :team="teams['D1']" />
    <JugendWidget id="D2" :team="teams['D2']" />
    <JugendWidget id="D3" :team="teams['D3']" />
    <JugendWidget id="D4" :team="teams['D4']" />
    <JugendWidget id="D5" :team="teams['D5']" />
    <JugendWidget id="E1" :team="teams['E1']" />
    <JugendWidget id="E2" :team="teams['E2']" />
    <JugendWidget id="E3" :team="teams['E3']" />
    <JugendWidget id="F1" :team="teams['F1']" />
    <JugendWidget id="F2" :team="teams['E3']" />
    <JugendWidget id="G1" :team="teams['G1']" />
    <JugendWidget id="G2" :team="teams['G2']" />
  </section>
</template>

<!---- Style ---------------------------------------------------->

<style lang="scss" scoped>
section {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-around;
}
</style>
