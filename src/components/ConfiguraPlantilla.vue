<template>
    <div class="row">
        <div class="col text-center">
            Complete los datos de la tarjeta.
        </div>
    </div>

    <div class="row">
        <div class="col">
            {{ tarjeta_conf }}
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

const props = defineProps(['tarjeta_conf'])
const emit = defineEmits(['tarjeta_conf_upd']) 

const params = ref({})

</script>