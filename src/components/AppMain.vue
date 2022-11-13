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
    },
    computed: {
        charactersNumber() {
            return this.store.characters.length;
        }
    }
}
</script>

<template>
    <div class="ms-container">
        <section>
            <div class="howMany mb-3" v-if='this.store.searchCategory !=="" '>
                You found {{charactersNumber}} characters!
            </div>
            <div class="row row-cols-5">
                <div class="col" v-for="character in store.characters" :key="character.char_id">
                    <CharacterCard :character="character" />
                </div>
            </div>
        </section>
    </div>
</template>

<style lang="scss" scoped>
    .howMany {
        background-color: #2e3a46;
        padding: 1rem;
        color: white;
    }

    section {
        background-color: white;
        padding: 2rem;

        h1 {
            color: white;
        }
    }
</style>