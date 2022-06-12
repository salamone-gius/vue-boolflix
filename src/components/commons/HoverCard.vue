<template>
    <div class="hover-card">
        <img class="card-img" src="https://via.placeholder.com/150" alt="">
        <div class="hover-info">
            <h2>Titolo:
                <span></span> 
            </h2>
            <h4>Titolo originale:
                <span></span>
            </h4>
            <h4>Lingua originale:
                <span></span>
            </h4>
            <h4>Voto:
                <span></span>
            </h4>
            <h4>Trama:
                <span></span>
            </h4>
        </div>
    </div>
</template>

<script>
export default {
    name: 'HoverCard',
}
</script>

<style lang="scss" scoped>
.hover-card {
    width: 15.4375rem;
    height: 23.1875rem;
    position: relative;
    cursor: pointer;
    
    .card-img {
        opacity: 1;
        display: block;
        width: 100%;
        height: 100%;
        height: auto;
        transition: .6s ease;
        backface-visibility: hidden;
    }

    .hover-info {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        padding: 3rem 1rem;
        transition: .6s ease;
        opacity: 0;

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