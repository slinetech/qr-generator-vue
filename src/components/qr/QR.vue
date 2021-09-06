<template>
    <div class="container">
        <vue-qr :text="text" qid="testid"></vue-qr>
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

</style>