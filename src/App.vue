<script setup>
import { reactive } from 'vue';
import Cabeca from './components/Cabecalho.vue';
import Corpo from './components/Corpo.vue';
import Rodape from './components/Rodape.vue';

const estado = reactive({
    valor1: 0,
    valor2: 0,
    resul: 0,
    cal: 'soma',
});

function pegaVal1(evento) {
    estado.valor1 = evento.target.value || 0;
    estado.valor1 = parseFloat(estado.valor1);
    getCal();
}

function pegaVal2(evento) {
    estado.valor2 = evento.target.value || 0;
    estado.valor2 = parseFloat(estado.valor2);
    getCal();
}

function pegaOperador(evento) {
    estado.cal = evento.target.value;
    getCal();
}

const getCal = () => {
    switch (estado.cal) {
        case 'somar':
            estado.resul = estado.valor1 + estado.valor2;
            break;
        case 'subtrair':
            estado.resul = estado.valor1 - estado.valor2;
            break;
        case 'multiplicar':
            estado.resul = estado.valor1 * estado.valor2;
            break;
        case 'dividir':
            estado.resul = estado.valor2 === 0 ? 'Undefined' : estado.valor1 / estado.valor2;
            break;
        default:
            estado.resul = 0; // Valor padrão para evitar resultados inesperados
    }
};
</script>

<template>
<div class="container mt-5">
    <form>
        <div class="card bg-transparent border-light-subtle" style="width: 500px;">
            <Cabeca />
            <Corpo
                :get-val1="pegaVal1"
                :get-val2="pegaVal2"
                :res="estado.resul"
                :get-cal="pegaOperador"
            />
            <Rodape />
        </div>
    </form>
</div>
</template>

<style scoped>
.container {
    margin: 11vh 10vh;
}
</style>
