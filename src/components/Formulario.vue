<script setup>
    const props = defineProps(['atualizaCampo1', 'valorCampo1', 'atualizaCampo2', 'valorCampo2', 'trocarOperacao', 'operacao']);
</script>

<template>
    <main>
        <div class="row">
            <div class="col-md-3">
                <input @keyup="props.atualizaCampo1" :value="props.valorCampo1" type="number" placeholder="Digite o primeiro número" class="form-control">
            </div>
            <div class="col-md-1 d-flex justify-content-center align-items-center">
                <span v-if="props.operacao === 'somar'">+</span>
                <span v-else-if="props.operacao === 'subtrair'">-</span>
                <span v-else>x</span>
            </div>
            <div class="col-md-3">
                <input @keyup="props.atualizaCampo2" :value="props.valorCampo2" type="number" placeholder="Digite o segundo número" class="form-control">
            </div>
            <div class="col-md-5">
                <select @change="props.trocarOperacao" class="form-control">
                    <option value="somar">Somar</option>
                    <option value="subtrair">Subtrair</option>
                    <option value="multiplicar">Multiplicar</option>
                </select>
            </div>
        </div>
    </main>
</template>