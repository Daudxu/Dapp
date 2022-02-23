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
      // web3Model: new Web3(new Web3.providers.HttpProvider('http://127.0.0.1:8545'))
    }
  },
  methods: {
    async test () {
      if (typeof window.ethereum !== 'undefined') {
        const ethereum = window.ethereum
        ethereum.autoRefreshOnNetworkChange = false;
        try {
          await ethereum.enable()
          const provider = window['ethereum']
          const web3 = new Web3(provider)
          var contract = "0xe470FAdd73f692a85443fccbD0a806a00DFdff6e"
          const CONTRACTAbi = [{ "inputs": [{ "internalType": "address", "name": "account", "type": "address" }], "name": "balanceOf", "outputs": [{ "internalType": "uint256", "name": "", "type": "uint256" }], "stateMutability": "view", "type": "function" }]
          var myContract = new web3.eth.Contract(CONTRACTAbi, contract)
          console.log(myContract)
          // myContract.methods.balanceOf(accounts[0]).call({from: contract}, function(error, result){
          //     console.log(error, result)
          // });
          // let fromAddress = accounts[0];
          // let amount = 1 * Math.pow(10, 18);
          // let toAddress = "0xE9189Ae0Bb5238050e8e2253dC7Bb88b9531E903";
          // web3.eth.sendTransaction({
          //   gas: 21000,
          //   gasPrice: 5000000000,
          //   from: fromAddress,
          //   to: toAddress,
          //   value: amount
          // }, (err, result) => {
          //   console.log("转账Hash=", result)
          //   console.log("err=", err)
          // })
          // ethereum.on('accountsChanged', function (accounts) {
          //   console.log("当前账户发生更改：" + accounts)
          // })
          // ethereum.on('networkChanged', function (networkVersion) {
          //   console.log("networkChanged" + networkVersion)
          // })
        } catch (e) {
          console.log(e)
        }
      }
      // console.log(myContract) balanceOf
      // await this.myContract.methods.mint(account, id, count, '0x0').send({ from: account, })
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
