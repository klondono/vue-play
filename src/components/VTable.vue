<template>
    <div>
        <Vuetable
        api-url="apiURL"
        :fields="fields"
        ></Vuetable>
    </div>
</template>

<script>
import {Vuetable} from './node_modules/vuetable-2/src';

    export default {
        components: {
            Vuetable
        },
        props: {
            apiURL: {
                type: String,
                required: true
            },
            fields: {
                type: Array,
                required: true
            }
        },
       data() {
           return {
           }
       }, 
       methods: {
       },
    }
</script>

<style scoped>

</style>