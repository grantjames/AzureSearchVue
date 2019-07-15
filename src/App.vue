<template>
    <div id="app">
        <search-box @searched="searched"/>

        <p><span v-show="searchTerm">You searched for: </span>{{ searchTerm }}</p>
    </div>
</template>

<script>
import SearchBox from './components/SearchBox.vue'

export default {
    name: 'app',
    data() {
        return {
            searchTerm: ""
        }
    },
    components: {
        SearchBox
    },
    methods: {
        searched(searchTerm) {
            this.searchTerm = searchTerm;
        }
    }
}
</script>

<style>

</style>
