<template>
    <section>
        <strong>
            {{ tempoDecorrido }}
        </strong>
    </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
    name:'Cronometro',
    props: {
        tempoEmSegundos: {
            type: Number,
            default: 0
        }
    },

    computed:{ //função espera receber uma função getter e o valor retornado é um ref calculado
        tempoDecorrido () : string {
            return new Date(this.tempoEmSegundos * 1000).toISOString().substr(11,8)
        }

    },


})
</script>

<style scoped></style>