<template>
  <countTo class="count" end='125000' autoPlay="true" duration='3000'></countTo>
  <br/>
  <countTo class="count" end='125000' autoPlay="true" duration='3000' prefix="前缀" suffix="后缀"></countTo>
  <br/>
  <countTo class="count" end='125000' autoPlay="true" duration='3000' prefix="自定义分隔" separator="❤🧡💛💚💙💜🤎🖤🤍"></countTo>
  <br/>
  <countTo class="count" end='125000' autoPlay="true" duration='3000' prefix="无分隔" separator=""></countTo>
  <br/>
  <countTo class="count" end='125000.5555' autoPlay="true" duration='2000' prefix="保留小数" decimals="2"></countTo>
  <br/>
  <countTo
      class="count"
      ref="countToRef"
      :end='countConfig.num'
      :autoPlay="countConfig.autoPlay"
      :duration='countConfig.time'
      @click="start()"
  >
  </countTo>
</template>

<script setup>
import countTo from './components/countTo.vue'
import {reactive, ref} from "vue";
const countConfig = reactive({
  num: 9800,
  autoPlay: false,
  time: 1000
})

const countToRef = ref(null);
const start = () => {
  countToRef.value.startCount();
}
</script>

<style scoped lang="less">
.count{
  font-size: 24px;
  color: darkcyan;
}
</style>
