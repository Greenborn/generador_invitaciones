<template>
    <div class="row">
        <div class="col text-center">
            Puede compartir la tarjeta y/o descargarla
        </div>
    </div>

    <div class="row">
        <div class="col">
            <TarjetaPreview :tarjeta_conf="tarjeta_conf" ref="tarjet_prev_cmp"/>
        </div>
    </div>

    <div class="row justify-content-center">
        <div class="col-auto">
            <Button severity="info" label="Compartir" @click="compartir" />
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'
import TarjetaPreview from './TarjetaPreview.vue';

defineExpose({ update })

const props = defineProps(['tarjeta_conf'])

const tarjet_prev_cmp = ref()

function compartir(){
    alert("funcionalidad en desarrollo")
}

function update(){
    tarjet_prev_cmp.value.update()
}
</script>