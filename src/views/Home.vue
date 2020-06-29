<template>
  <div class="home">
      <button @click="makePayment">PayNow</button>
  </div>
</template>

<script>
/* eslint-disable */
export default {
  name: "home",
  components: {},
  methods: {
    makePayment: function() {
      var options = {
        key: "",
        amount: "100",
        name: "TEST APP",
        currency: "INR",
        description: "Purchase Description",
        image: "",
        handler: response => {
          this.verifySignature(response);
        },
        prefill: {
          name: "Ashwani Kumar",
          email: "lnd.ashwini07@gmail.com",
          contact: "8983726311"
        },
        notes: {
          address: "Hello World"
        },
        theme: {
          color: "#528ff0"
        }
      };
      var rzp1 = new Razorpay({ ...options });
      rzp1.open();
    },
    verifySignature: function() {
    }
  }
};
</script>

<style scoped>
button {
  background: #528ff0;
  border: none;
  padding: 8px 30px;
  margin: 16px;
  color: white;
}
</style>
