<template>
    <div class="container mt-60">
        <div class="row justify-content-center">
            <div class="col-md-6 col-sm-12 text-center">
                <vue-qr :text="text" qid="testid"></vue-qr>
            </div>
            <div class="col-12 text-center bk-word">
                {{text}}
            </div>
        </div>
    </div>
</template>

<script>
import VueQr from 'vue-qr'
export default {
    name: 'QR',
    props:{
        text: String
    },
    components: {
        VueQr
    },
    methods: {}
}
</script>

<style scoped>
    .mt-60{
        margin-top: 60px;
    }
    .bk-word{
        word-break: break-all;
    }
</style>