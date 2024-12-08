<template>
    <div class="row">
        <div class="col text-center">
            Puede compartir la tarjeta y/o descargarla
        </div>
    </div>

    <div class="row">
        <div class="col">
            {{ tarjeta_conf }}
        </div>
    </div>
</template>

<script setup>

const props = defineProps(['tarjeta_conf'])

</script>