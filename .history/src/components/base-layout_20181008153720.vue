<template>
    <div class="containter-wrap">
        <div class="show-calculate-wrap">{{ calculate }}</div>
        <div id="asd" class="show-num-wrap">{{ digital }}</div>
        <div class="btn-wrap">
            <btn v-for="(item, index) in btnArr" :key="index + item" :itemData="item" @test="testClick"></btn>
        </div>
    </div>
</template>

<script>
    import btn from './btn.vue'

    export default {
        name: 'baseLayout',
        components: {
            btn
        },
        data: () => {
            return {
                calculate: '',
                digital: 0,
                btnArr: [
                    {
                        content: 'c',
                        className: 'gay', 
                        value: 'c',                 
                    },
                    {
                        content: '+/-',
                        className: 'gay',
                        value: '0',
                    },
                    {
                        content: '%',
                        className: 'gay',
                        value: '%',
                    },
                    {
                        content: '÷',
                        className: 'orange',
                        value: '÷',
                    },
                    {
                        content: '7',
                        className: 'brown',
                        value: '7',
                    },
                    {
                        content: '8',
                        className: 'brown',
                        value: '8',
                    },
                    {
                        content: '9',
                        className: 'brown',
                        value: '9',
                    },
                    {
                        content: '×',
                        className: 'orange',
                        value: '×',
                    },
                    {
                        content: '4',
                        className: 'brown',
                        value: '4',
                    },
                    {
                        content: '5',
                        className: 'brown',
                        value: '5',
                    },
                    {
                        content: '6',
                        className: 'brown',
                        value: '6',
                    },
                    {
                        content: '-',
                        className: 'orange',
                        value: '-',
                    },
                    {
                        content: '1',
                        className: 'brown',
                        value: '1',
                    },
                    {
                        content: '2',
                        className: 'brown',
                        value: '2',
                    },
                    {
                        content: '3',
                        className: 'brown',
                        value: '3',
                    },
                    {
                        content: '+',
                        className: 'orange',
                        value: '+',
                    },
                    {
                        content: '0',
                        className: 'n0',
                        value: '0',
                    },
                    {
                        content: '.',
                        className: 'brown',
                        value: '.',
                    },
                    {
                        content: '=',
                        className: 'orange',
                        value: '=',
                    },


                ],
               nowNum: '',
               shang: 0,
               nowcount: 0,
               nowthen: 0,
            }
            
        },
        methods: {
            testClick (op) {


                

                switch (op.value) {
                    case 'c':
                       
                        this.nowNum = 0;
                        this.calculate = '';
                        this.nowcount = 0;
                        this.nowthen = 0;
                        
                    break;
                    case '0': case '1': case '2': case '3': case '4': case '5': case '6': case '7': case '8': case '9':
                   
                            this.nowNum += op.value;
                      

                      
                    break;
                    case '÷': case '×': case '+': case '-':
                         this.calculate = this.nowNum + ' ' + op.value;  
                         this.nowthen = op.value; 

                    break;
                    case '=':
                       this.nowcount = this.nowNum + this.calculate
                    break;                  
                }

                    
                // this.nowNum  = this.nowcount;

                this.digital = this.nowNum;
            }
        }
    }
</script>

<style scoped>

.containter-wrap {
    width: 540px;
    height: 960px;
    background-color: black;
    margin: auto;
}

.show-calculate-wrap {
    color: gray;
    padding: 143px 25px 0 0;
    font-size: 40px;
    height: 40px;
    line-height: 40px;
    text-align: right;
}

.show-num-wrap {
    color: #fff;
    padding: 0px 25px 0 0;
    font-size: 88px;
    height: 88px;
    line-height: 88px;  
    text-align: right;
    margin: 0px 0px 40px 0px;
}
</style>
