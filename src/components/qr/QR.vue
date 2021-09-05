<template>
    <div class="container">
        <vue-qr text="Hello world!" :callback="test" qid="testid"></vue-qr>
    </div>
</template>

<script>
import VueQr from 'vue-qr'
export default {
    name: 'QR',
    components: {
        VueQr
    },
    methods: {
        test(dataUrl,id){
            console.log(dataUrl, id);
        }
    }
}
</script>

<style scoped>

</style>