<template>
  <div>
    <v-btn @click="getIp">Get IPaddress</v-btn>
    <p>{{ ip }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      ip: "0.0.0.0",
    };
  },
  methods: {
    async getIp() {
      this.ip = await this.$axios.$get("http://icanhazip.com");
    },
  },
};
</script>