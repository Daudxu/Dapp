<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      this is a Dapp Web3 Test project,<br>
      check out the.
    </p>
    <h3>交易</h3>
    <ul>
      <li><a target="_blank"
           rel="noopener">eth.sendTransaction()</a></li>
    </ul>
    <h3>签名</h3>
    <ul>
      <li><a target="_blank"
           rel="noopener">eth.sendTransaction()</a></li>
      <li><a target="_blank"
           rel="noopener">dai.transfer()</a></li>
      <li><a target="_blank"
           rel="noopener">box.getProfile()</a></li>
      <li><a target="_blank"
           rel="noopener">sign()</a></li>
      <li><a target="_blank"
           rel="noopener">personal.sign()</a></li>
    </ul>
    <h3>其他</h3>
    <ui>
      <li><a target="_blank"
           rel="noopener"
           @click="test()">Balances()</a></li>
    </ui>

  </div>
</template>

<script>
import Web3 from 'web3'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data () {
    return {
      web3Model: new Web3(new Web3.providers.HttpProvider('http://127.0.0.1:8545'))
    }
  },
  methods: {
    test () {
      console.log(this.web3Model)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="stylus">
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
  cursor: pointer;
}
</style>
