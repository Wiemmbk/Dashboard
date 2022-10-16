<template>
  <div>
      {{ aboutFile }}
  </div>
</template>

<script>
import aboutJson from "../../about.json";
export default {
  // name: "AboutJson",
  
  created() {
      this.aboutFile = aboutJson;
  },
  data() {
      return {
          aboutJson
      };
  },
};
</script>

<style>

</style>