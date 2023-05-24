<script setup>
const props = defineProps(['operacao', 'numero1', 'numero2'])
</script>

<template>
    <div class="operation">
        <h2>Selecione a operação</h2>
            <select @change="props.operacao">
                <option value="+">+</option>
                <option value="-">-</option>
                <option value="*">*</option>
                <option value="/">/</option>
        </select>
    </div>
    <div>
        <input @keyup="props.numero1" require type="number" placeholder="Insira o primeiro número" />
        <input @keyup="props.numero2" require type="number" placeholder="Insira o segundo número" />

    </div>
</template>

<style scoped>
input {
    margin: 30px;
    padding: 4px;
    border-radius: 4px;
}
</style>