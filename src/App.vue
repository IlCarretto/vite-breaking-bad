<script>
import axios from "axios";
import AppMain from "./components/AppMain.vue";
import AppSearch from "./components/AppSearch.vue";
import {store} from "./store";

export default {
  components: {
    AppMain,
    AppSearch
  },
  data() {
    return {
      store
    }
  },
  created() {
    this.chooseCategory();
  },
  methods: {
    chooseCategory() {
      // console.log(store.searchCategory);
      let apiUrl = "https://www.breakingbadapi.com/api/characters"
      
      // Se non c'è alcuna opzione, mostrare tutti i personaggi XX
      
      // Se viene scelta l'opzione breaking bad, mostrare i personaggi di breaking bad
      // Se viene scelta l'opzione better call saul, mostrare i personaggi di better call saul
      if (this.store.searchCategory) {
        apiUrl += `?category=${this.store.searchCategory}`
      } 

      axios
      .get(apiUrl)
      .then((resp) => {
        this.store.characters = resp.data;
      });
    }
  }
}
</script>

<template>
<main>
  <AppSearch @searchSelect="chooseCategory" />
  <AppMain/>
</main>
</template>

<style lang="scss">
@use "./styles/general.scss" as *;

</style>
