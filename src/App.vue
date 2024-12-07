<template>

<Tabs value="0">
  <TabList>
      <Tab value="0">Elegir Plantilla</Tab>
      <Tab value="1">Agregar Contenido</Tab>
      <Tab value="2">Descargar y Compartir</Tab>
  </TabList>
  <TabPanels>

      <TabPanel value="0">
          <SelectorPlantilla />
      </TabPanel>

      <TabPanel value="1">
          <ConfiguraPlantilla />
      </TabPanel>

      <TabPanel value="2">
          <ResultadoFinal />
      </TabPanel>

  </TabPanels>
</Tabs>

</template>

<script setup>
import { ref } from 'vue'

import SelectorPlantilla from './components/SelectorPlantilla.vue';
import ConfiguraPlantilla from './components/ConfiguraPlantilla.vue';
import ResultadoFinal from './components/ResultadoFinal.vue';

</script>

<style>

</style>
