<template>
    <div class="is-flex is-align-items-center is-justify-content-space-between">
        <Cronometro_ :tempoEmSegundos="tempoEmSegundos" />
        <button type="button" @click="iniciar" :disabled="cronometroRodando">
            <span class="icon">
                <i class="fas fa-play"></i>
            </span>
            <span>Play</span>
        </button>
        <button type="button" @click="finalizar" :disabled="!cronometroRodando">
            <span class="icon">
                <i class="fas fa-stop"></i>
            </span>
            <span>Stop</span>
        </button>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Cronometro_ from './Cronometro.vue';
export default defineComponent({
    name: 'Temporizador_',
    emits: [
        'aoTempoFinalizado'
    ],
    components: {
        Cronometro_
    },
    data() {
        return {
            tempoEmSegundos: 0,
            cronometro: 0,
            cronometroRodando: false
        }
    },
    methods: {
        iniciar() {
            this.cronometroRodando = true;
            this.cronometro = setInterval(() => {
                this.tempoEmSegundos += 1;
            }, 1000)
        },
        finalizar() {
            this.cronometroRodando = false;
            clearInterval(this.cronometro);
            this.$emit('aoTempoFinalizado', this.tempoEmSegundos);
            this.tempoEmSegundos = 0;
        }
    }
})
</script>