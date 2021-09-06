<template>
    <div class="container">
        <div class="row">
            <div class="col-6">
                <div class="mb-3">
                    <label for="exampleFormControlInput1" class="form-label title-cm">Text to Corvert</label>
                    <input ref="inputTextToConvert" v-model="textoConvert" type="text" class="form-control" id="exampleFormControlInput1" placeholder="https://www.google.com">
                </div>
                <button @click="generate()" class="primary">Generate</button>
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
</style>