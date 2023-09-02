<template>
    <Box_>
        <div class="columns">
            <div class="column is-7">
                {{ tarefa.descricao || 'Tarefa sem descrição' }}
            </div>
            <div class="column">
                <Cronometro_ :tempoEmSegundos="tarefa.duracaoEmSegundos" />
            </div>
        </div>
    </Box_>
</template>

<script lang="ts">
import { PropType, defineComponent } from 'vue';
import Cronometro_ from './Cronometro.vue';
import Box_ from './Box.vue';
import ITarefa from '@/interfaces/ITarefa';
export default defineComponent({
    name: 'Tarefa_',
    components: {
        Cronometro_,
        Box_
    },
    props: {
        tarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    }
});
</script>