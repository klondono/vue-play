<template>
    <div>
        <Vuetable
        ref="vuetable"
        :api-url="apiURL"
        :fields="fields"
        :httpMethod="httpMethod"
        :httpOptions="httpOptions"
        :detail-row-component="detailRowComponent"
        :track-by="trackBy"
        ></Vuetable>
    </div>
</template>

<script>
// import Vue from 'vue'
import Vuetable from '../../node_modules/vuetable-2/src/components/Vuetable.vue';
/* import detailrow from './DetailRow.vue';
Vue.component('my-detail-row', detailrow) */

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
            },
            httpMethod: {
                type: String,
                required: true
            },
            httpOptions: {
                type: Object,
                required: false
            },
            trackBy: {
                type: String,
                required: false
            },
            detailRowComponent: {
                type: String,
                required: false
            } 
        },
       data() {
           return {
           }
       }, 
       mounted() {

           this.$refs.vuetable.toggleDetailRow(2);
       },
       methods: {


       },
    }
</script>

<style scoped>

</style>