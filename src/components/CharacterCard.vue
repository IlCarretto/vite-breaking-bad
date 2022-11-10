<script>
export default {
    name: "CharacterCard",
    props: {
        character: Object
    }
}
</script>

<template>
    <div class="ms-card text-center">
        <div class="ms-card-img">
            <img :src="character.img" alt="">
        </div>
        <div class="ms-card-text">
            <h4>{{character.name}}</h4>
            <p>{{character.category}}</p>
            <p>{{character.status}}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .ms-card {
        background-color: #2e3a46;

        .ms-card-img {
            display: flex;
            justify-content: center;
            height: 200px;
            padding: .5rem 0;
        }

        .ms-card-text {
            
            h4 {
                color: white;
                font-size: 1rem;
                text-transform: uppercase;
            }
        }
    }

</style>