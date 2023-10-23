<template>
    <div>
        <input v-model="numero1" @input="calcular" />
        <select v-model="operacao" @change="calcular">
            <option value="soma">Soma (+)</option>
            <option value="subtracao">Subtração (-)</option>
            <option value="multiplicacao">Multiplicação (*)</option>
            <option value="divisao">Divisão (/)</option>
        </select>
        <input v-model="numero2" @input="calcular" />
        <p>Resultado: {{ resultado }}</p>
    </div>
</template>

<script>
export default {
    data() {
        return {
            numero1: 0,
            numero2: 0,
            operacao: 'soma',
            resultado: 0,
        };
    },
    methods: {
        calcular() {
            if (this.operacao === 'soma') {
                this.resultado = Number(this.numero1) + Number(this.numero2);
            } else if (this.operacao === 'subtracao') {
                this.resultado = Number(this.numero1) - Number(this.numero2);
            } else if (this.operacao === 'multiplicacao') {
                this.resultado = Number(this.numero1) * Number(this.numero2);
            } else if (this.operacao === 'divisao') {
                this.resultado = Number(this.numero1) / Number(this.numero2);
            }
        },
    },
};
</script>
