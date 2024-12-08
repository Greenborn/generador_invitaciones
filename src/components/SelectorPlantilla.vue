<template>
    <div class="row">
        <div class="col text-center">
            Seleccione el tipo de invitación y la plantilla a usar.
        </div>
    </div>

    <div class="row">
        <div class="col" >
            
            <Accordion>
                <AccordionPanel v-for="cat_plantilla in CONFIG.plantillas" :key="cat_plantilla" :value="cat_plantilla.id">
                    <AccordionHeader>{{ cat_plantilla.nombre }}</AccordionHeader>
                    <AccordionContent>
                        <div class="row">

                            <div class="col" v-for="plantilla in cat_plantilla.plantillas" :key="plantilla">
                                <Card @click="plantilla_seleccionada(plantilla)">
                                    <template #title><b></b></template>
                                    <template #content>

                                        {{ plantilla }}
                                        
                                    </template>
                                </Card>
                            </div>

                        </div>
                    </AccordionContent>
                </AccordionPanel>
            </Accordion>

        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

import { CONFIG } from '../config'

const emit = defineEmits(['tarjeta_conf']) 
const props = defineProps(['tarjeta_conf'])

function plantilla_seleccionada(plantilla){
    emit("tarjeta_conf", plantilla)
}
</script>