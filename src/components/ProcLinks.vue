<template>
    <div class="container">
        <table>
            <thead>
                <tr>
                    <th>Action Status</th>
                    <th>Id</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>{{rowData.name}}</td>
                </tr>
                <tr v-for="(item) of journalEntries" v-bind:key="item.TxnId">
                    <td>{{item.ActionStatus}}</td>
                    <td>{{item.TxnId}}</td>
                </tr> 
            </tbody>
        </table>
    </div>
</template>

<script>

    export default {
        props: {
            rowData: {
                type: Object,
                required: true
            },
            rowIndex: {
                type: Number
            }
        },
       data() {
           const self = this;
           return {
               journalEntries: [{ActionStatus: "Await Approval", TxnId: 1},{ActionStatus: "Rejected", TxnId: 2}],
               dataFromParent: self.$parent.permissions
           }
       }, 
       methods: {
           name() {
               
           }
       },
    }
</script>

<style scoped>
.container {
    display: flex;
    justify-content: center;
}
table {  
    color: #333;
    font-family: Helvetica, Arial, sans-serif;
    width: 640px; 
    border-collapse: 
    collapse; border-spacing: 0; 
}

td, th {  
    border: 1px solid transparent; /* No more visible border */
    height: 30px; 
    transition: all 0.3s;  /* Simple transition for hover effect */
}

th {  
    background: #DFDFDF;  /* Darken header a bit */
    font-weight: bold;
}

td {  
    background: #FAFAFA;
    text-align: center;
}

/* Cells in even rows (2,4,6...) are one color */        
tr:nth-child(even) td { background: #F1F1F1; }   

/* Cells in odd rows (1,3,5...) are another (excludes header cells)  */        
tr:nth-child(odd) td { background: #FEFEFE; }  

tr td:hover { background: #666; color: #FFF; }  
/* Hover cell effect! */
</style>