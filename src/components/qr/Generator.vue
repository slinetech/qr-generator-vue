<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-4 col-sm-12">
                <div class="mb-3">
                    <label for="exampleFormControlInput1" class="form-label title-cm">Text to Corvert</label>
                    <input ref="inputTextToConvert" v-model="textoConvert" type="text" class="form-control" id="exampleFormControlInput1" placeholder="https://www.google.com">
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
            showQr: false
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
            if (this.textoConvert != '') {
                this.textConvert = this.textoConvert;
                this.textoConvert = '';
                this.showQr = true;
            }else{
                this.showQr=false;
            }
            this.$refs.inputTextToConvert.focus();
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