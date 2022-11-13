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
            <div class="div mb-3">
                <input class="form-control" type="text">
                <select class="form-select" v-model="store.searchCategory" @change="$emit('searchSelect')">
                    <option selected value="">Select Category</option>
                    <option v-for="(option, index) in categoryOptions" :key="index">{{option}}</option>
                </select>
                <button class="btn btn-primary">
                    a
                </button>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
    .div {
        display: flex;
    }
</style>