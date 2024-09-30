<script setup>
const props = defineProps(['estado']);
</script>

<template>
    <form class="form-group">
        <div class="row mb-3">
            <div class="col-md-6">
                <input type="number" v-model.number="props.estado.numero1" class="form-control"
                    placeholder="Número 1" />
            </div>
            <div class="col-md-6">
                <input type="number" v-model.number="props.estado.numero2" class="form-control"
                    placeholder="Número 2" />
            </div>
        </div>
        <div class="row">
            <div class="col-md-6">
                <select v-model="props.estado.operacao" class="form-control">
                    <option value="soma">Soma</option>
                    <option value="subtracao">Subtração</option>
                    <option value="multiplicacao">Multiplicação</option>
                    <option value="divisao">Divisão</option>
                </select>
            </div>
        </div>
    </form>
</template>

<style scoped>
    select:hover{
        cursor: pointer;
        color: #2140c9;
        font-weight: 500;
    }

    input, select {
        height: 45px;
        font-size: 18px;
        margin-bottom: 15px;
    }
</style>
