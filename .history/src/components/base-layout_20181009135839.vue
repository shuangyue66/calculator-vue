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
                calculate: '',
                digital: 0,
                firstNum: '',
                secondNum: '',
                operation: '',
                lastClick: ''
            }
            
        },
        methods: {
            testClick (op) {
                // 当是c的时候，直接清空所有的，变为初始值，所以直接就可以return不需要再走过多的逻辑
                if (op.content === 'c') {
                    this.calculate = ''
                    this.digital = 0,
                    this.firstNum = ''
                    this.secondNum = ''
                    this.lastClick = ''
                    this.operation = ''
                    return
                }
                    switch(op.content) {
                        case '0': case '1': case '2': case '3': case '4': case '5': case '6': case '7': case '8': case '9':
                            if (this.lastClick === 'operation') {
                                this.secondNum += op.content
                            } else {
                                this.firstNum += op.content
                            }
                                this.lastClick = 'Num'
                        break;
                        case '÷': case '×': case '+': case '-':
                            this.calculate = this.firstNum + op.content
                            this.operation = op.content
                            this.lastClick = 'operation'
                        break;
                        case '=':
                            this.digital = Number(this.firstNum) + Number(this.secondNum)
                            this.calculate = ''
                            this.firstNum = his.digital
                            this.secondNum = ''
                        break;
                    }   
                    
                        if (this.lastClick === 'operation') {

                            } else if(op.content === '=') {


                                }else {
                                    if (this.operation) {
                                        this.digital = this.secondNum        
                                    } else {
                                        this.digital = this.firstNum
                                    }
                        }   
                    
            }
        }
    }

    // outer:
                // switch (op.value) {
                //     case 'c':
                //         this.nowNum = '';
                //         this.first = '';
                //         this.calculate = '';
                //         this.nowcount = 0;
                //         this.nowthen = 0;
                //         this.shang = 0;
                //         this.xia = '';
                //         break;
                //     case '0': case '1': case '2': case '3': case '4': case '5': case '6': case '7': case '8': case '9':
                //         if(this.shang === 0){
                //             this.first += op.value;
                //             this.nowNum = this.first;
                //         } else {
                //             this.xia += op.value;
                //             this.nowNum = this.xia;
                //         }
                //         break;
                //     case '÷': case '×': case '+': case '-': 
                //         this.calculate = this.nowNum + ' ' + op.value;  
                //         this.nowthen = op.value; 
                //         this.shang = this.nowNum;
                //         this.isEqual = false
                //         break;
                //     case '=':
                //         inner: 
                //         switch(this.nowthen){
                //             case '+':
                //                 this.nowNum = Number(this.shang) + Number(this.nowNum);
                //                 break inner;
                //             case '-':
                //                 this.nowNum = Number(this.shang) - Number(this.nowNum);
                //                 break inner;
                //             case '×':
                //                 this.nowNum = Number(this.shang) * Number(this.nowNum);
                //                 break inner;
                //             case '÷':
                //                 this.nowNum = Number(this.shang) / Number(this.nowNum);
                //                 break inner;
                //             case '=':
                            
                //                 break inner;
                //         }
                //         this.isEqual = true
                //         this.calculate = '';
                //     break outer;                 
                // }   
                        
                // if (op.value === 'c') {
                //     this.digital = 0
                // } else {
                //     this.digital = this.nowNum;
                // }
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