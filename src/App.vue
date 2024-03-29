<script setup>
import Web3 from 'web3';
import Web3Api from './components/Web3Api.vue';
//实例化web3
var web3 = new Web3(Web3.givenProvider || "wss://goerli.infura.io/ws/v3/0fda17b26c574dca81d0069f6150ffe8");
// console.log(web3);
</script>

<template>
<h1>Hello World</h1>
<van-button color="linear-gradient(to right, #ff6034, #ee0a24)">
  欢迎来到我的钱包
</van-button>
<Suspense>
  <Web3Api></Web3Api>
</Suspense>

</template>

<style scoped>
h1 {
  color: red;
}
</style>
