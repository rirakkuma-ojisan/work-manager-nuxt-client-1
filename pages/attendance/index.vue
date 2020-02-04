<template>
  <div class="animated fadeIn">
    <div>
      attendance/index.vue
      <div>
        <button v-on:click="showMessage">port3001で立ち上げているサーバーからデータを取得</button>
      </div>
      <div class="border-dark">
        response : {{res}}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
        res: ''
    }
  },
  methods: {
    showMessage() {
      const response = this.$axios.$get("/api/monthly_attendance")
        .then(response => {
          console.log(response);
          this.res = response
        })
        .catch(error => {
          console.log(error);
        })
    }
  }
}
</script>
