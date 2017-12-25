<template>
    <div>
    {{key}}
        <!-- <proclinks></proclinks> -->
        <vtable
            :apiURL="apiURL"
            :fields="fields"
            :httpMethod="httpMethod"
            :httpOptions="httpOptions"
            :detail-row-component="detailComponent"
            :track-by="trackBy"
        ></vtable>
    </div>
</template>

<script>
//import proclinks from './ProcLinks.vue';
import Vue from 'vue'
import vtable from './VTable.vue';
import detailrow from './DetailRow.vue';
Vue.component('my-detail-row', detailrow)


    export default {
        components: {
            // proclinks,
            vtable
        },
       data() {
           return {
               key: "This is main js where we will store some info.",
               permissions: {Modify: true, Approve: true, Discard: false, Remodify: false, View: true},
               apiURL: 'https://vuetable.ratiw.net/api/users',
               //apiURL: 'https://jsonplaceholder.typicode.com/posts',
               fields: ['id','name', 'email','birthdate','nickname','gender'],
               //httpMethod:'post',
               httpMethod:'get',
               httpOptions: {name: 'firstName', lastName: 'lastName'},
               trackBy:'id',
               detailComponent: 'my-detail-row'
           }
       }, 
       methods: {
           name() {
               
           }
       },
    }
</script>

<style scoped>

</style>