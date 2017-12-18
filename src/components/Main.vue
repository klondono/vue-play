<template>
    <div>
    {{key}}
        <proclinks></proclinks>
    </div>
</template>

<script>
import proclinks from './ProcLinks.vue';

    export default {
        components: {
            proclinks
        },
       data() {
           return {
               key: "This is main js where we will store some info.",
               permissions: {Modify: true, Approve: true, Discard: false, Remodify: false, View: true}
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