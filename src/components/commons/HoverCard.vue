<template>
    <div class="hover-card">
        <img class="card-img" :src="poster" :alt="posterAlt">
        <div class="hover-info">
            <h2>Titolo:
                <span>{{title}}</span> 
            </h2>
            <h4>Titolo originale:
                <span>{{originalTitle}}</span>
            </h4>
            <h4>Lingua originale:
                <span>{{originalLanguage}}</span>
            </h4>
            <h4>Voto:
                <span>{{vote}}</span>
            </h4>
            <h4>Trama:
                <span>{{plot}}</span>
            </h4>
        </div>
    </div>
</template>

<script>
export default {
    name: 'HoverCard',

    props: {
        title: String,
        originalTitle: String,
        originalLanguage: String,
        vote: String,
        plot: String,
        poster: String,
        posterAlt: String,
    }
}
</script>

<style lang="scss" scoped>
.hover-card {
    min-width: 15.4375rem;
    height: 23.1875rem;
    position: relative;
    cursor: pointer;
    margin: 1.5rem;
    
    .card-img {
        opacity: 1;
        display: block;
        width: 100%;
        height: 100%;
        transition: .6s ease;
        backface-visibility: hidden;
        overflow-y: hidden;
    }

    .hover-info {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        padding: 1rem;
        transition: .6s ease;
        opacity: 0;
        overflow-y: scroll;

        h2, h4 {
            color: rgb(255, 255, 255);

            span {
                color: #b6b5b5;
            }
        }
    }

    &:hover .card-img {
        opacity: 0.2;
    }

    &:hover .hover-info {
        opacity: 1;
    }

}
</style>