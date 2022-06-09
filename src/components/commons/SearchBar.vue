<template>
    <form class="input-group my-3">
        <input v-model="searchThis" :placeholder="inputPlaceholder" type="text" class="form-control" aria-label="Recipient's username" aria-describedby="button-addon2">
        <button class="btn btn-outline-secondary" type="button" id="button-addon2">{{buttonText}}</button>
    </form>
</template>

<script>
export default {
    name: 'SearchBar',

    data() {
        return {
            searchThis: "",
        }
    },

    props: {
        buttonText: String,
        inputPlaceholder: String,
    }
}
</script>

<style lang="scss" scoped>

</style>