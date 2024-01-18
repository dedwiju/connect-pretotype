<script setup>
import { ref } from 'vue'

const image = ref(false)
const stock = ref(false)
const unsold = ref(false)
const available = ref(false)

const addColumn = () => {
  if (!image.value) {
    image.value = true
    return
  }
  if (!stock.value) {
    stock.value = true
    return
  }
  if (!unsold.value) {
    unsold.value = true
    return
  }
  if (!available.value) {
    available.value = true
    return
  }
}
</script>

<template>
  <div class="item">
    <table class="table">
      <thead>
        <tr>
          <th scope="col" width="130px">품목코드</th>
          <th scope="col" width="170px">품목명</th>
          <th scope="col" width="110px" v-if="image">이미지</th>
          <th scope="col" width="130px" v-if="stock">재고수량</th>
          <th scope="col" width="110px" v-if="unsold">미판매</th>
          <th scope="col" width="140px" v-if="available">가용 재고</th>
          <th scope="col" class="plus" @click="addColumn">+</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th scope="row">1</th>
          <td>멀티 비타민</td>
          <td v-if="image"><img src="../assets/멀티 비타민.png" width="50px" /></td>
          <td v-if="stock">85</td>
          <td v-if="unsold">10</td>
          <td v-if="available">75</td>
        </tr>
        <tr>
          <th scope="row">2</th>
          <td>레모네이드</td>
          <td v-if="image"><img src="../assets/레모네이드.jpg" width="50px" /></td>
          <td v-if="stock">80</td>
          <td v-if="unsold">3</td>
          <td v-if="available">77</td>
        </tr>
        <tr>
          <th scope="row">3</th>
          <td>통조림 참치</td>
          <td v-if="image"><img src="../assets/통조림 참치.jpg" width="50px" /></td>
          <td v-if="stock">45</td>
          <td v-if="unsold">5</td>
          <td v-if="available">40</td>
        </tr>
        <tr>
          <th scope="row">4</th>
          <td>포도 주스</td>
          <td v-if="image"><img src="../assets/포도 주스.jpg" width="50px" /></td>
          <td v-if="stock">45</td>
          <td v-if="unsold">10</td>
          <td v-if="available">35</td>
        </tr>
        <tr>
          <th scope="row">5</th>
          <td>콜라</td>
          <td v-if="image"><img src="../assets/콜라.jpg" width="50px" /></td>
          <td v-if="stock">40</td>
          <td v-if="unsold">5</td>
          <td v-if="available">35</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped>
.item {
  height: 600px;
  border-left: 1px solid var(--color-border);
}

.item .table {
  vertical-align: middle;
}

.item .table tr {
  height: 70px;
}

.item .table .plus {
  cursor: pointer;
}
</style>
