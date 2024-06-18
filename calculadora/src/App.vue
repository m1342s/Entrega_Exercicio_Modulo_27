<script setup>
import { reactive } from "vue";
import Formulario from "./components/Formulario.vue";

const estado = reactive({
  filtro: "multiplicacao",
  n1: 0,
  n2: 0,
});

const multiplicacao = ({n1, n2}=estado) => {
  return n1 * n2;
};
const adicao =  ({n1, n2}=estado) => {
  return n1 + n2;
};
const subtracao =  ({n1, n2}=estado) => {
  return n1 - n2;
};
const divisao =  ({n1, n2}=estado) => {
  return n1 / n2;
};



const calculadora = () => {
  const { n1, n2, filtro } = estado;

  if ((n1, n2)) {
    switch (filtro) {
      case "divisao":
        return divisao();
      case "multiplicacao":
        return multiplicacao();
      case "adicao":
        return adicao();
      case "subtracao":
        return subtracao();
    }
  }
};
</script>

<template>
  <h1 class="d-flex justify-content-center mt-3">Calculadora aritmética</h1>
  <Formulario
    :trocaFiltro="(event) => (estado.filtro = event.target.value)"
    :valorN1="(event) => (estado.n1 =Number(event.target.value))"
    :valorN2="(event) => (estado.n2 =Number(event.target.value))"
  />
  <div class="d-block pb-3">
  Resultado:<span>{{ calculadora() }}</span>
  
  </div>
</template>

<style scoped></style>
