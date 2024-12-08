<template>

<Tabs v-model:value="tab_actual">
  <TabList>
      <Tab value="0">Elegir Plantilla</Tab>
      <Tab value="1">Agregar Contenido</Tab>
      <Tab value="2">Descargar y Compartir</Tab>
  </TabList>
  <TabPanels>

      <TabPanel value="0">
          <SelectorPlantilla :tarjeta_conf="tarjeta_conf" @tarjeta_conf="template_selected" />
      </TabPanel>

      <TabPanel value="1">
          <ConfiguraPlantilla  :tarjeta_conf="tarjeta_conf" @tarjeta_conf_upd="template_configured"/>
      </TabPanel>

      <TabPanel value="2">
          <ResultadoFinal  :tarjeta_conf="tarjeta_conf" />
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

function template_selected( plantilla ){
    tab_actual.value = "1"
    tarjeta_conf.value.plantilla = plantilla
}

function template_configured( config ){
    tab_actual.value = "2"
    tarjeta_conf.value.configuracion = config
}
</script>

<style>

</style>
