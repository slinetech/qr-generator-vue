<template>
    <div class="container">
        <div v-if="msg.showMsg" class="alert" :class="{'alert-success': msg.succ, 'alert-danger': msg.err,'d-none': !msg.showMsg}" role="alert">
            {{ msg.data }}
        </div>
        <div class="row justify-content-center">
            <div class="col-md-4 col-sm-12">
                <div class="mb-3">
                    <label for="inputTextConvert" class="form-label title-cm text-center label-form">Text to Corvert</label>
                    <input ref="inputTextToConvert" v-model="textoConvert" type="text" class="form-control" id="inputTextConvert" placeholder="https://www.google.com">
                </div>
            </div>
            <div class="col-md-2 col-sm-12 pl-0-pr-0">
                <button @click="generate()" class="btn btn-primary btn-generate mt-30">Generate</button>
            </div>
        </div>
        <div v-if="showQr">
            <QR :text="textConvert"/>
        </div>
    </div>
</template>

<script>
import QR from './QR.vue'

export default {
    name: 'Generator',
    data: () => {
        return {
            textConvert: '',
            textoConvert: '',
            showQr: false,
            msg:{
                showMsg: false,
                err: false,
                succ: false,
                data:''
            }
        }
    },
    components: {
        QR
    },
    mounted(){
        //console.log(screen.width);
    },
    methods:{
        generate(){
            if (this.textoConvert != '') {// Validate input is't empty
                this.textConvert = this.textoConvert;
                this.textoConvert = '';
                this.showQr = true;
                this.changeMsg('succ');
                console.log(this.msg);
            }else{
                this.changeMsg('err');
                console.log(this.msg);
                this.showQr=false;
            }
            this.$refs.inputTextToConvert.focus();
        },
        changeMsg(type){
            this.msg.showMsg=true;
            if( type == 'succ' ){
                this.msg.err= false;
                this.msg.succ = true;
                this.msg.data = "Successfull"
            }else{
                this.msg.succ= false;
                this.msg.err= true;
                this.msg.data="Error!! -> Input is Empty"
            }
            setTimeout(()=>{this.msg.showMsg=false},3000);
        }
    }
}
</script>
<style scoped>
    .title-cm{
        font-weight: 600;
    }
    .btn-generate{
        width: 100%;
        background-color: #8bc34a;
        border-color: #8bc34a;
    }
    .form-control:focus{
        border-color: #8bc34a !important;
        box-shadow: 0 0 0 0.25rem rgb(139 195 74 / 25%);
    }
    .btn-generate:hover{
        background-color: #88dd27;
        border-color: #88dd27;
    }
    .label-form{
        width: 100%;
        text-transform: uppercase;
    }
    /*Small devices (landscape phones, 576px and up)*/
    @media (min-width: 576px) {
        .mt-30{
            margin-top: 0;
        }
    }

    /*Medium devices (tablets, 768px and up)*/
    @media (min-width: 768px) {
        .mt-30{
            margin-top: 30px;
        }
        .pl-0-pr-0{
            padding-left: 0;
            padding-right: 0;
        }
    }

    /*Large devices (desktops, 992px and up)*/
    @media (min-width: 992px) {

    }

    /*Extra large devices (large desktops, 1200px and up)*/
    @media (min-width: 1200px) {

    }
</style>