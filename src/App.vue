<script setup>
import TheWelcome from './components/TheWelcome.vue'

import { ref } from 'vue'

const table = ref(false)

const click = (event) => {
  table.value = true
  event.target.classList.add('active')
  console.log(event.target)
}
</script>

<template>
  <header>
    <div class="wrapper">
      <ul class="list-group">
        <li class="list-group-item" @click="click">재고/유통</li>
        <li class="list-group-item">생산/제조</li>
        <li class="list-group-item">영업/판매</li>
        <li class="list-group-item">구매/발주</li>
        <li class="list-group-item">경리/회계</li>
        <li class="list-group-item">인사/급여</li>
        <li class="list-group-item">협업</li>
        <li class="list-group-item">메일</li>
      </ul>
    </div>
  </header>

  <main>
    <TheWelcome v-if="table" />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
  display: flex;
  place-items: center;
  justify-content: center;
  padding-right: calc(var(--section-gap) / 2);
}

header .wrapper {
  display: flex;
  place-items: flex-start;
  flex-wrap: wrap;
}

header .wrapper .list-group .list-group-item {
  width: 200px;
  text-align: center;
  cursor: pointer;
}
</style>
