<script setup>
    const props = defineProps(['trocarNumero1', 'trocarNumero2', 'trocaOperacao',
    'trocaSoma', 'trocaSubtracao', 'trocaMultiplicacao', 'trocaDivisao'])
</script>

<template>
    <form>
        <div class="row">
            <div class="col">
                <input @change="props.trocarNumero1" required type="number"
                    placeholder="Digite aqui um número" class="form-control mb-4 mt-4 w-75">
                <input @change="props.trocarNumero2" required type="number"
                    placeholder="Digite aqui outro número" class="form-control mb-4 mt-4 w-75">
            </div>
            <div class="col-md-2">
                <select @change="props.trocaOperacao" class="form-control mb-4 mt-4">
                    <option value="default">Escolha a operação desejada</option>
                    <option @change="props.trocaSoma" value="soma">Somar</option>
                    <option @change="props.trocaSubtracao" value="subtrair">Subtrair
                    </option>
                    <option @change="props.trocaMultiplicacao" value="multiplicar">Multiplicar</option>
                    <option @change="props.trocaDivisao" value="dividir">Dividir</option>
                </select>
            </div>
        </div>
    </form>
</template>