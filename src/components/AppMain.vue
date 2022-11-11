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
    <div class="ms-container">
        <section>
            <div class="row row-cols-5">
                <div class="col" v-for="character in store.characters" :key="character.char_id">
                    <CharacterCard :character="character" />
                </div>
            </div>
        </section>
    </div>
</template>

<style lang="scss" scoped>
    section {
        background-color: white;
        padding: 2rem;

        h1 {
            color: white;
        }
    }
</style>