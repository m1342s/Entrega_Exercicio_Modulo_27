<script setup>
const props=defineProps(["valorN1","valorN2","trocaFiltro","calculadora"])
</script>


<template>
  <form class="ms-4 d-flex flex-column justify-content-center ">
    <div class="d-flex flex-column mx-auto">
      <div class="d-block pb-3">
        <label for="numero1">Número 1</label>
        <input @keyup="props.valorN1"
          style="width: 320px"
          type="number"
          step="0.01"
          class="form-control"
          id="numero1"
        />
      </div>
      <div class="d-block pb-3">
        <label for="numero2">Número 2</label>
        <input
        @keyup="props.valorN2"
          style="width: 320px"
          type="number"
          step="0.01"
          id="numero2"
          class="form-control"
        />
      </div>
     
      <select @change="props.trocaFiltro" class="form-control" name="" id="select">
        <option value="multiplicacao">Multiplicação</option>
        <option value="adicao">Adição</option>
        <option value="subtracao">Subtração</option>
        <option value="divisao">Divisão</option>
      </select>
    </div>
  </form>
</template>
