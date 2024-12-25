<script lang="ts" setup>
import pdfLink from '@/assets/aufnahmeantrag.pdf'
import SamIcon from '../components/SamIcon.vue'
</script>

<!---- Html ---------------------------------------------------->

<template>
  <div class="container">
    <h1>Mitglied werden</h1>
    <div class="formular"><img src="https://klarenthal.s3.eu-north-1.amazonaws.com/general/formular.jpg" alt=""></div>
    
    <a :href="pdfLink" target="_blank" rel="noopener noreferrer">
      <div>
        <SamIcon :size="30" color="000000">material-symbols:download-rounded</SamIcon
        ><span>Anmeldeformular herunterladen</span>
      </div>
    </a>
  </div>
</template>

<!---- Style ---------------------------------------------------->

<style lang="scss" scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  h1 {
    margin-bottom: 30px;
    font-size: 45px;
  }
}


.formular {
  width: 300px
}
a {
  color: rgb(86, 86, 94);
  text-decoration: underline;
  margin-top: 20px;
  margin-bottom: 50px;
  div {
    display: flex;
    justify-content: center;
    span {
      margin-left: 5px;
    }
  }
}
</style>
