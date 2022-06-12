<template>
    <div class="logo">
        <a class="navbar-brand" href="#">        
            <img :class="imageClass" :src="imageSrc" :alt="imageAlt">
        </a>
    </div>
</template>

<script>
export default {
    name: 'LogoBox',

    props: {
        imageSrc: String,
        imageAlt: String,
        imageClass: String,
    }
}
</script>

<style lang="scss">
img {
    width: 12.5rem;
}
</style>