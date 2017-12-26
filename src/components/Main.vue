<template>
    <div>
    {{key}}
        <!-- <proclinks></proclinks> -->
        <vtable
            :apiURL="apiURL"
            :fields="fields"
            :httpMethod="httpMethod"
            :httpOptions="httpOptions"
            :detailRowComponent="detailComponent"
            :trackBy="trackBy"
            :append-params="vm"
        ></vtable>
    </div>
</template>

<script>
import proclinks from './ProcLinks.vue';
import Vue from 'vue'
import vtable from './VTable.vue';

Vue.component('proc-links', proclinks)


    export default {
        components: {
            vtable
        },
       data() {
           return {
               vm: {name: 'firstName', lastName: 'lastName'},
               key: "This is main js where we will store some info.",
               permissions: {Modify: true, Approve: true, Discard: false, Remodify: false, View: true},
               apiURL: 'https://vuetable.ratiw.net/api/users',
               //apiURL: 'https://jsonplaceholder.typicode.com/posts',
               fields: [{name: 'id', title: 'title'},{name: 'name', title: 'Title', callback: 'allcap'}, 'email','birthdate','nickname','gender'],
               //httpMethod:'post',
               httpMethod:'get',
               httpOptions: {},
               trackBy:'id',
               detailComponent: 'proc-links'
           }
       }, 
       mounted() {

       }
    }
</script>

<style scoped>

</style>