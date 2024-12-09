<template>
    <div class="row justify-content-center">
        <div class="col-auto">
            <div class="w-100">

                <div class="border" :style="{ 'height': tarjeta_conf?.plantilla?.dimensiones?.alto + 'px', 'width': tarjeta_conf?.plantilla?.dimensiones?.ancho + 'px' }">
                </div>

                <div class="elemento" v-for="elemento in configurable.elementos" :key="elemento" :style="{ 'left': elemento.posicion.x + 'px', 'top': elemento.posicion.y + 'px' }">
                    {{ elemento }}
                </div>

            </div>
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

    aux.elementos = []
    aux.elementos.push(
        {
            tipo: "color_fondo",
            valor: "#ffffff",
            posicion: { x: 0, y: 0 },
        }
    )

    return aux
}

</script>

<style scoped>
.elemento{
    position: absolute;
}
</style>