<template>
    <div class="hover-card">
        <img class="card-img" :src="poster" :alt="posterAlt">
        <div class="hover-info">
            <h3>Titolo:
                <span>{{title}}</span> 
            </h3>
            <h5>Titolo originale:
                <span>{{originalTitle}}</span>
            </h5>
            <h5>Lingua originale:
                <span>
                    {{originalLanguage}}
                    <img class="flag" :src="imageFlag">
                </span>
            </h5>
            <h5>Voto:
                <span v-if="vote === 0">non disponibile</span>
                <span v-else>
                    <i v-for="(i, index) in starVote(vote)" :key="index" class="fab fa-solid fa-star"></i>
                    <i v-for="(j, index) in (5 - starVote(vote))" :key="j[index]" class="fab fa-regular fa-star"></i>
                </span>
            </h5>
            <h5>Trama:
                <span>{{plot}}</span>
            </h5>
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
        vote: Number,
        plot: String,
        poster: String,
        posterAlt: String,
        imageFlag: String,
    },

    data() {
        return {
            flags: [
                "en",
                "it",
                "es",
                "de",
                "fr",
            ],
        }
    },

    methods: {
        starVote(vote) {
            let quinaryVote = Math.floor(vote / 2);
            return quinaryVote;
        }
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

        h3, h5 {
            color: rgb(255, 255, 255);

            span {
                color: #b6b5b5;

                img.flag {
                    width:1.6rem;
                }

                .fa-star {
                    color: yellow;
                    font-size: 1.1rem;
                }
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