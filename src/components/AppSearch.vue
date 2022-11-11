<script>
import {store} from "../store";

export default {
    name: "AppSearch",
    data() {
        return {
            store,
            categoryOptions: ["Breaking Bad", "Better Call Saul"]
        }
    }
}
</script>

<template>
    <section>
        <h1>Breaking Bad Api</h1>
        <div class="container">
            <select class="form-select mb-3" v-model="store.searchCategory" @change="$emit('searchSelect')">
                <option selected value="">Select Category</option>
                <option v-for="(option, index) in categoryOptions" :key="index">{{option}}</option>
            </select>
        </div>
    </section>
</template>

<style lang="scss" scoped>

</style>