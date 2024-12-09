<template>

<Tabs v-model:value="tab_actual">
  <TabList>
      <Tab value="0">Elegir</Tab>
      <Tab value="1">Editar</Tab>
      <Tab value="2">Compartir</Tab>
  </TabList>
  <TabPanels>

      <TabPanel value="0">
          <SelectorPlantilla :tarjeta_conf="tarjeta_conf" @tarjeta_conf="template_selected" />
      </TabPanel>

      <TabPanel value="1">
          <ConfiguraPlantilla  :tarjeta_conf="tarjeta_conf" @tarjeta_conf_upd="template_configured" ref="configura_cmp"/>
      </TabPanel>

      <TabPanel value="2">
          <ResultadoFinal  :tarjeta_conf="tarjeta_conf" ref="resultado_cmp" />
      </TabPanel>

  </TabPanels>

</Tabs>

</template>

<script setup>
import { ref } from 'vue'

import SelectorPlantilla from './components/SelectorPlantilla.vue';
import ConfiguraPlantilla from './components/ConfiguraPlantilla.vue';
import ResultadoFinal from './components/ResultadoFinal.vue';

const tab_actual = ref("0")

const tarjeta_conf = ref({
    "plantilla": {},
    "configuracion": {}
})

const resultado_cmp = ref()
const configura_cmp = ref()

function template_selected( plantilla ){
    tab_actual.value = "1"
    tarjeta_conf.value.plantilla = plantilla
    resultado_cmp.value.update()
    configura_cmp.value.update()
}

function template_configured( config ){
    tab_actual.value = "2"
    tarjeta_conf.value.configuracion = config
    resultado_cmp.value.update()
    configura_cmp.value.update()
}
</script>

<style>

</style>
