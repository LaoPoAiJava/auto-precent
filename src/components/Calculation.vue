<script setup>
  // 导入reactive
  import { reactive, ref } from 'vue'

  // 声明数组
  const state = reactive([])

  // 数组实例
  let datas = [
    { denominator: 2, result: 50 },
    { denominator: 3, result: 33.3 },
    { denominator: 4, result: 25 },
    { denominator: 5, result: 20 },
    { denominator: 5.5, result: 18.2 },
    { denominator: 6, result: 16.7 },
    { denominator: 7, result: 14.3 },
    { denominator: 8, result: 12.5 },
    { denominator: 9, result: 11.1 },
    { denominator: 10.5, result: 9.5 },
    { denominator: 11, result: 9.1 },
    { denominator: 11.5, result: 8.7 },
    { denominator: 11.8, result: 8.5 },
    { denominator: 12, result: 8.3 },
    { denominator: 13, result: 7.7 },
    { denominator: 14, result: 7.1 },
    { denominator: 15, result: 6.7 },
    { denominator: 15.5, result: 6.5 },
    { denominator: 16, result: 6.25 },
    { denominator: 17, result: 5.9 },
    { denominator: 18, result: 5.6 },
    { denominator: 19, result: 5.3 },
    { denominator: 20, result: 5 },
    { denominator: 21, result: 4.8 },
    { denominator: 23, result: 4.3 },
    { denominator: 36, result: 2.8 },
    { denominator: 43.5 , result: 2.3 }
    // { denominator: , result:  },
  ]
  state.push(...datas)

  let isShow = ref(false);

  function displayHandler() {
    if(isShow.value) {
      isShow.value = false;
    } else {
      isShow.value = true;
    }
  }

</script>

<template>
  <div class="main">
    <div v-for="(item, index) in datas" :key="index" class="box">
      <div class="zhi">{{ item.result }}%</div>
      <div class="dengyu">=</div>
      <div class="fenzi">
        <div>1</div>
        <div>——</div>
        <div v-if="isShow">{{ item.denominator }}</div>
        <!-- <div v-else><input type="text" name="" id="input"></div> -->
      </div>
    </div>
    <button @click="displayHandler">开关</button>
  </div>
</template>

<style scoped>
  .main {
    display: flex;
    flex-wrap: wrap;
    justify-content: flex-start; /* 从主轴头部开始, 从左往右排列 */
    align-items: center;
    width: 1000px;
    height: 600px;
    margin: 0 auto;
    color: #E1E1E1;
  }
  
  .box {
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 120px;
    height: 60px;
    background-color: #636363;
    margin: 10px 20px;
    border-radius: 12px; /* 圆角 */
  }

  .fenzi {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .fenzi div:nth-child(2) {
    margin: -5px 0;
  }

</style>