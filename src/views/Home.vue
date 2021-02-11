<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import axios from "axios";

export default {
  name: "Home",
  components: {
    HelloWorld,
  },
  created: async () => {
    // const url = "http://localhost:8000/items/itemlist";
    // const res = await axios.get(url);
    // console.log(res.data);
    const apiUrl =
      "https://public-api.tracker.gg/v2/fortnite/standard/profile/pc/MBC_KEITA";
    const apiKey = "3912364f-1c9a-48d2-b117-1ddcd4ebd075";
    const config = {
      headers: {
        "Content-Type": "application/json",
        "TRN-Api-Key": apiKey,
      },
    };
    const response = await axios.post(apiUrl, config);
    console.log(response.data);
  },
};
</script>
