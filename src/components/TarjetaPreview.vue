<template>
    <div class="row">
        <div class="col">
            Vista previa de la tarjeta
        </div>
    </div>

    <div class="row">
        <div class="col">
            {{ configurable }}
        </div>
    </div>
</template>

<script setup>
import { ref }  from 'vue'

defineExpose({ update })

const props = defineProps(['tarjeta_conf'])

const configurable = ref(get_configurable(props.tarjeta_conf))

function update(){
    configurable.value = get_configurable(props.tarjeta_conf)
}

function get_configurable(tarjeta_conf) {
    let aux = {}

    if (tarjeta_conf?.plantilla?.parametros == undefined) return aux

    let keys_ = Object.keys(tarjeta_conf.plantilla?.parametros)
    for (let i = 0; i < keys_.length; i++)
        aux[keys_[i]] = {...tarjeta_conf.plantilla.parametros[keys_[i]], value: '' }

    return aux
}

</script>