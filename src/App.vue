<template>
  <div id="app">
    <h1 class="title"> Money Counter </h1>
    <div class="columns">
      <div class="column">
        <div class="field">
          <div class="control">
            Dollars:
            <input class="input" type="number" placeholder="Dollars" v-model.number="dollar" @change="checkNegative" min="0" />
          </div>
        </div>
      </div>
      <div class="column">
        <div class="field">
          <div class="control">
            Pennies:
            <input class="input" type="number" placeholder="Pennies" v-model.number="penny" @change="checkNegative" min="0" />
          </div>
        </div>
      </div>      
    </div>
    <div class="columns">
      <div class="column">
        <div class="field">
          <div class="control">
            Fives:
            <input class="input" type="number" placeholder="Fives" v-model.number="five" @change="checkNegative" min="0" />
          </div>
        </div>
      </div>
      <div class="column">
        <div class="field">
          <div class="control">
            Nickles:
            <input class="input" type="number" placeholder="Nickles" v-model.number="nickle" @change="checkNegative" min="0" />
          </div>
        </div>
      </div>      
    </div>
        <div class="columns">
      <div class="column">
        <div class="field">
          <div class="control">
            Tens:
            <input class="input" type="number" placeholder="Tens" v-model.number="ten" @change="checkNegative" min="0" />
          </div>
        </div>
      </div>
      <div class="column">
        <div class="field">
          <div class="control">
            Dimes:
            <input class="input" type="number" placeholder="Dimes" v-model.number="dime" @change="checkNegative" min="0" />
          </div>
        </div>
      </div>      
    </div>
    <div class="columns">
      <div class="column">
        <div class="field">
          <div class="control">
            Twenties:
            <input class="input" type="number" placeholder="Twenties" v-model.number="twenty" @change="checkNegative" min="0" />
          </div>
        </div>
      </div>
      <div class="column">
        <div class="field">
          <div class="control">
            Quarters:
            <input class="input" type="number" placeholder="Quarters" v-model.number="quarter" @change="checkNegative" min="0" />
          </div>
        </div>
      </div>      
    </div>
    <div class="columns">
      <div class="column">
        <div class="field">
          <div class="control">
            Fifties:
            <input class="input" type="number" placeholder="Fifties" v-model.number="fifty" @change="checkNegative" min="0" />
          </div>
        </div>
      </div>
      <div class="column has-text-left">
        <p>Total Bills: ${{ totalBills() }}</p>
        <p>Total Coins: ${{ totalCoins() }}</p>
        <!--p>Total: ${{ result || 0 }}</p-->
        <p>Total: ${{ total() }}</p>  
       
      </div>  
    </div>
    <div class="columns">
      <div class="column">
        <div class="field">
          <div class="control">
            Hundreds:
            <input class="input" type="number" placeholder="Hundreds" v-model.number="hundred" @change="checkNegative" />
          </div>
        </div>
      </div>
      <div class="column">
        <button class="button is-info is-rounded is-fullwidth" @click="reset">
          <span class="icon">
            <i class="fas fa-undo"></i>
          </span>
          <span>Reset</span>
        </button>  
      </div>  
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
      return {
        dollar: '0',
        five: '0',
        ten: '0',
        twenty: '0',
        fifty: '0',
        hundred: '0',
        penny: '0',
        nickle: '0',
        dime: '0',
        quarter: '0'
      }
    },
    methods: {
      totalBills() {
        var totdoallar = (parseInt(this.dollar) * 1)
        var totfive = (parseInt(this.five) * 5)
        var totten = (parseInt(this.ten) * 10)
        var tottwenty = (parseInt(this.twenty) * 20)
        var totfify = (parseInt(this.fifty) * 50)
        var tothundred = (parseInt(this.hundred) * 100)
        var total = totdoallar + totfive + totten + tottwenty + totfify + tothundred
        return Math.round(total * 100) / 100
      },
      totalCoins() {
        var totpenny = (parseInt(this.penny) * .01)
        var totnickle = (parseInt(this.nickle) * .05)
        var totdime = (parseInt(this.dime) * .10)
        var totquarter = (parseInt(this.quarter) * .25)
        var total = totpenny + totnickle + totdime + totquarter
        return Math.round(total * 100) / 100
      },
      total(){
        return this.totalBills() + this.totalCoins()
      },
      reset() {
        this.dollar = '0';
        this.five = '0';
        this.ten = '0';
        this.twenty = '0';
        this.fifty = '0';
        this.hundred = '0';
        this.penny = '0';
        this.nickle = '0';
        this.dime = '0';
        this.quarter = '0';
      },
      checkNegative() {
        if (this.dollar < 0){
          this.dollar = 0;
        }
        if (this.five < 0){
          this.five = 0;
        }
        if(this.ten < 0 ){
          this.ten = 0;
        }
        if (this.twenty < 0){
          this.twenty = '0';
        }
        if (this.fifty < 0){
          this.fifty = '0';
        }
        if (this.hundred < 0){
          this.hundred = '0';
        }
        if (this.penny < 0){
          this.penny = '0';
        }
        if (this.nickle < 0){
          this.nickle = '0';
        }
        if (this.dime < 0){
          this.dime = '0';
        }
        if (this.quarter < 0){
          this.quarter = '0';
        }
      }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0px auto;
  margin-top: 60px;
  width:50%;
  padding: 2em;
  box-shadow: 0 0 5px 5px #666;
}
</style>
