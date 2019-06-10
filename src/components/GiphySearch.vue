<template>
    <div class="search">
        <input type="text" v-model="message" placeholder="Search..." name="search"/>
    </div>
</template>

<script>
export default {
    name: "GiphySearch",
    props: {
        message: String
    }
}
</script>

<style scoped>

</style>