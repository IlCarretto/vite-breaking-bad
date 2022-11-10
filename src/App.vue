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

    }
  }
}
</script>

<template>
<AppMain/>
</template>

<style lang="scss" scoped>
@use "./styles/general.scss" as *;

</style>
