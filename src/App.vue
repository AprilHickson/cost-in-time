<template>
  <div class="main">
    <div class="main__wrapper">
      <div class="main__wrapper__input">
        <input type='text' placeholder="Cost of the item" v-model="costOfItem">
        <input type='text' placeholder="Pay per hour" v-model="payPerHour">
      </div>
      <h2>{{ this.time() }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      costOfItem: 0, 
      payPerHour: 0
    }
  },
  methods: {
    time: function () {
      console.log(this.hasValidValues());
      if(this.hasValidValues()) {
        return this.costOfItem/this.payPerHour;
      }
    },
    hasValidValues: function () {
      if(this.costOfItem && 
        this.payPerHour && 
        this.costOfItem !== undefined && 
        this.payPerHour !== undefined) {
        return true;
      }
      return false;
    }
  }
}
</script>

<style lang="less">
body, html {
  height: 100%;
  margin: 0;
}
.main {
  display:flex;
  flex-direction: column;
  height: 100%;

  &__wrapper {
    display:flex;
    margin: auto;
    flex-direction: column;

    &__input {
    display:flex;
    flex-direction: row;
    }
  }
}
</style>
