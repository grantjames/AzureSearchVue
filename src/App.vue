<template>
    <div id="app">
        <div class="columns">
            <div class="column">
                <p class="subtitle is-5">
                    <strong>Azure Search</strong> Vue Demo
                </p>
            </div>

            <div class="column is-three-quarters">
                <search-box @searched="searched"/>
            </div>
        </div>   

        <div class="columns">
            <div class="column">

                <nav class="panel">
                    <p class="panel-heading">Filters</p>
                    <a href="#" class="panel-block is-active">
                        Filter 1
                    </a>
                    <a href="#" class="panel-block">
                        Filter 2
                    </a>
                    <a href="#" class="panel-block">
                        Filter 3
                    </a>
                    <div class="panel-block">
                        <button class="button is-link is-outlined is-fullwidth">
                            Remove all filters
                        </button>
                    </div>
                </nav>

                <nav class="panel">
                    <p class="panel-heading">Facets</p>
                    <a href="#" class="panel-block is-active">
                        Facet 1
                    </a>
                    <a href="#" class="panel-block">
                        Facet 2
                    </a>
                    <a href="#" class="panel-block">
                        Facet 3
                    </a>
                    <div class="panel-block">
                        <button class="button is-link is-outlined is-fullwidth">
                            Remove all facets
                        </button>
                    </div>
                </nav>
            </div>
            <div class="column is-three-quarters">
                <p v-show="searchTerm">Your search for '{{ searchTerm }}' produced {{ searchResults.length }} results</p>
                <hr>
                <div v-for="result in searchResults" :key="result.id">
                    <p>
                        <strong>{{ result.title }}</strong>
                        <br>
                        {{ result.description }}
                    </p>
                    
                    <hr>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import SearchBox from './components/SearchBox.vue'

export default {
    name: 'app',
    data() {
        return {
            searchTerm: "test",
            searchResults: [
                {
                    id: 1,
                    title: "Test title",
                    "description": "This is a random description. Blah blah, whatever."
                },
                {
                    id: 2,
                    title: "Another title",
                    "description": "Blah blah, whatever. This is a random description."
                },
                {
                    id: 3,
                    title: "And a last one here",
                    "description": "No more results"
                }
            ]
        }
    },
    components: {
        SearchBox
    },
    methods: {
        searched(searchTerm) {
            this.searchTerm = searchTerm;

            // axios call to call api with search term and populate searchResults data
        }
    }
}
</script>

<style>

</style>
