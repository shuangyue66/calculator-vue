<template>
    <div class="btn" :class="itemData.className" @click="btnClick">
       {{ itemData.content }}
    </div>
</template>

<script>
    export default {
        name: 'btn',
        components: {
            
        },
        props: {
            itemData: {
                type: Object,
                default: () => {
                    return  {}
                }
            }
        },
        data: () => {
       return {
                  
           }
        },
        methods: {
            btnClick () {      
                this.$emit('test', this.itemData)              
            },
        }
    }
</script>

<style scoped>
    .btn {
        float: left;
        width: 111px;
        height: 111px;
        line-height: 111px;
        font-size: 48px;
        border-radius: 100%; 
        border-color: black;
        margin: 0 0 18px 18px; 
        transition: background-color .5s, color .5s;
    }
    
    .gay {
        background-color: #a6a6a6;
        color: black;
    }

    .orange {
        background-color: #f19a39;
        color: #ffffff;
    }

    .brown {
        background-color: #343434;
        color: #ffffff;
    }

    .btn:hover{
     background-color: rgba(255,255,255,0.9) ;
     color: black;
    }

    .n0 {
        width: 199px;
        border-radius: 60px;
        text-align: left;
        padding-left: 42px;
        background-color: #343434;
        color: #ffffff;

    }
</style>
