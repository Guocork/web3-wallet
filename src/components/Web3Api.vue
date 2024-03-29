<script setup>
import Web3 from 'web3';
import { ref } from 'vue';
//实例化web3
var web3 = new Web3(Web3.givenProvider || "wss://goerli.infura.io/ws/v3/0fda17b26c574dca81d0069f6150ffe8");

//创建账户  注意：这个方法每次执行都会创建新的账号
// const account = web3.eth.accounts.create("123");
// console.log(account);


//获取余额
// const mount = ref(-1);
// mount.value = await web3.eth.getBalance(account.address);

//单位转化
const num = web3.utils.toWei('0.3', 'ether');
console.log(num);


//转账操作
const transaction = async () => {
    //1.构建转账参数
    //获取账户交易次数  记录该账户的交易次数
    // const nonce = await web3.eth.getTransactionCount();

    //获取预计转账的gas费用
    // const gasPrice = await web3.eth.gasPrice();

    //转账金额 以wei作为单位
    const value = web3.utils.toWei('0.01', 'ether');
    console.log(value);

    const rawTx = {
        from: account.address,
        to: "",
        nonce,
        gasPrice,
        value,
        data: ""
    }
};
</script>

<template>
<h1>API</h1>
<div>余额：{{ mount }}</div>
<van-button plain type="primary" @click="transaction">开始转账</van-button>
</template>

<style scoped>

</style>