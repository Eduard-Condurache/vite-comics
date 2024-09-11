<script>
export default {
    props: {
        cardTitle: String,
        cardImg: String
    }
};
</script>

<template>
    <div class="card-item">
        <div class="seriesimage-container">
            <img :src="cardImg" :alt="cardTitle">
        </div>

        <div>
            <p>{{ cardTitle }}</p>
        </div> 
    </div>
</template>

<style lang="scss" scoped>
@use '../assets/scss/partials/mixins.scss' as *;
@use '../assets/scss/partials/variables' as *;

.card-item {
    width: 200px;
    margin: 0 auto;
    padding-bottom: 40px;

    .seriesimage-container img {
        width: 190px;
        height: 190px;
        object-fit: cover;
        object-position: top;
        }

    p {
        padding: 15px 0;
        text-transform: uppercase;
        font-size: 0.9rem;
    }
}
</style>