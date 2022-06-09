<template>
    <div class="input-group my-3">
        <input type="text" class="form-control" :placeholder="inputPlaceholder" aria-label="Recipient's username" aria-describedby="button-addon2">
        <button class="btn btn-outline-secondary" type="button" id="button-addon2">{{buttonText}}</button>
    </div>
</template>

<script>
export default {
    name: 'SearchBar',

    props: {
        buttonText: String,
        inputPlaceholder: String,
    }
}
</script>

<style lang="scss" scoped>

</style>