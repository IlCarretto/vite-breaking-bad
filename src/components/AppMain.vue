<script>
import { store } from "../store";
import CharacterCard from "./CharacterCard.vue";

export default {
    name: "AppMain",
    components: {
        CharacterCard
    },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <main>
        <h1>Breaking Bad Api</h1>
        <div class="ms-container">
            <div class="row row-cols-5">
                <div class="col" v-for="character in store.characters" :key="character.char_id">
                    <CharacterCard :character="character" />
                </div>
            </div>
        </div>
    </main>
        
</template>

<style lang="scss" scoped>
    main {
        background-color: #2e3a46;
        width: 100%;
        height: 100%;

        .ms-container {
            background-color: white;
            padding: 2rem;
        }

        h1 {
            color: white;
        }
    }
</style>