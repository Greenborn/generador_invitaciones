<template>
    <div class="row">
        <div class="col text-center">
            Complete los datos de la tarjeta.
        </div>
    </div>

    <div class="row">
        <div class="col">
            <TarjetaPreview :tarjeta_conf="tarjeta_conf" ref="tarjet_prev_cmp" />
        </div>
    </div>

    <div class="row justify-content-center">
        <div class="col-auto">
            <Button severity="info" label="Siguiente" @click="emit('tarjeta_conf_upd', params)" />
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'
import TarjetaPreview from './TarjetaPreview.vue';

defineExpose({ update })

const props = defineProps(['tarjeta_conf'])
const emit = defineEmits(['tarjeta_conf_upd']) 

const params = ref({})
const tarjet_prev_cmp = ref()

function update(){
    tarjet_prev_cmp.value.update()
}
</script>