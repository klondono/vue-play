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
import Vuetable from '../../node_modules/vuetable-2/src/components/Vuetable.vue';


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

       },
       updated() {
           const self = this;
           
           const table = self.$refs.vuetable;
           console.log('updated called')

           console.log(table.countTableData);
       },
       methods: {
           allcap (value) {
                return value.toUpperCase()
            },
            transform: function(data) {
                
                    let list = data.data;
                    for(let item of list) {
                        
                        this.$refs.vuetable.visibleDetailRows.push(item.id);

                    }

                    return data;
            }    
       },
    }
</script>

<style scoped>

</style>