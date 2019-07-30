<template>
    <div class="field has-addons">
        <div class="control">
            <input class="input" type="text" placeholder="Film name or actor" v-model="searchTerm">
        </div>
        <div class="control">
            <a class="button is-info" @click="search">
                Search
            </a>
        </div>
    </div>
</template>

<script>
export default {
    name: 'SearchBox',
    data() {
        return {
            searchTerm: ""
        }
    },
    methods: {
        search() {
            this.$emit('searched', this.searchTerm);
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
