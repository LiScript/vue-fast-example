<template>
  <div>
    测试公用方法
    <div>时间转时间戳:{{data1}}</div>
    <div>时间转时间戳:{{data2}}</div>
    <div>时间转时间戳:{{data3}}</div>
    <!-- <div>
      {{rowsData}}
    </div>-->
  </div>
</template>
<script>
/* eslint-disable */
import { isPhone } from "../../utils/validate";
export default {
  data() {
    return {
      data1: new Date().getTime(),
      data2: new Date().valueOf(),
      data3: Number(new Date()),
      rowsData: []
    };
  },
  created: function() {
    for (let x = 1; x <= 10000; x++) {
      this.rowsData = [...this.rowsData, x];
    }
    // console.log('aaa',isPhone(2))
  }
};
</script>
