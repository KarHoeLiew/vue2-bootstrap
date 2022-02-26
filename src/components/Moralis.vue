<template>
  <div id="moralis">
      <h2 class="greenFont">Moralis</h2>


  <button v-if="!user" @click="logIn">logIn</button>
  <button v-if="user" @click="logOut">LogOut</button>
  <button id="btn-get-stats" @click="getHello">Refresh Stats</button>

</div>
</template>

<script>
  import Moralis from 'moralis'
  export default {
    name: "App",
    components: {},
    data() {
      return {
        user: null
      }
    },
    created() {
      Moralis.initialize("lcQdvpuocydiTINjqXIV2PnhWXRNiaK1388zfZra");
      Moralis.serverURL = "https://5dtb1ksx37iw.usemoralis.com:2053/server";
      Moralis.start();
    },
    methods: {
      async logIn() {
        this.user = Moralis.User.current();
        if (!this.user) {
          this.user = await Moralis.authenticate();
        }
        console.log("logged in user:", this.user);
      },
      async logOut() {
        await Moralis.User.logOut();
        this.user = null
        console.log("logged out");
      }, 
      getStats() {
        const user = Moralis.User.current();
        if (user) {
          this.getUserTransactions(user);
        }
         this.getAverageGasPrices();
      },
      async getUserTransactions(user) {
        // create query
        const query = new Moralis.Query("EthTransactions");
        query.equalTo("from_address", user.get("ethAddress"));

        // run query
        const results = await query.find();
        console.log("user transactions:", results);
      },
      async getAverageGasPrices() {
        const results = await Moralis.Cloud.run("getAvgGas");
        console.log("average user gas prices:", results);
      },
      async getHello(){
        const result = await Moralis.Cloud.run("helloworld");
        console.log("success: ", result);
      }

    },  
    computed: {}
  }
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
}


.blueFont {
  color: blue;
  
}

.greenFont {
  color: green;
  font-size: 30px;
}

.redFont {
  color: red;
  font-size: 30px;
}

.redbg {
  background: red;
}
</style>
