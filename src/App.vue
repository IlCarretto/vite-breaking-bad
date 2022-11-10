<script>
import axios from "axios";
import AppMain from "./components/AppMain.vue";
import {store} from "./store";

export default {
  components: {
    AppMain,
  },
  data() {
    return {
      store
    }
  },
  created() {
    axios
    .get("https://www.breakingbadapi.com/api/characters")
    .then((resp) => {
      this.store.characters = resp.data;
      console.log(store.characters);
    })
  }
}
</script>

<template>
<AppMain/>
</template>

<style lang="scss">
@use "./styles/general.scss" as *;

</style>
