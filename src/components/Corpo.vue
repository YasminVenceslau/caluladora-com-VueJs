<script setup>
const props = defineProps(['getVal1', 'getVal2', 'getCal', 'res']);
</script>

<template>
    <div class="card-body text-info bg-transparent">
        <div class="card-title">
            <div class="row">
                <div class="col text-center">
                    <p class="text-center">{{ res }}</p>
                </div>
            </div>
        </div>
        <div class="card-body">
            <form class="text-center">
                <div class="row justify-content-center">
                    <div class="col-6">
                        <input
                            class="form-control bg-transparent border-info text-center"
                            type="number"
                            @input="getVal1"
                        />
                    </div>
                </div>
                <div class="row mt-2 justify-content-center">
                    <div class="col-8">
                        <select
                            class="form-select text-center bg-transparent border-info"
                            @change="getCal"
                        >
                            <option selected value="somar">+</option>
                            <option value="subtrair">-</option>
                            <option value="multiplicar">×</option>
                            <option value="dividir">÷</option>
                        </select>
                    </div>
                </div>
                <div class="row justify-content-center mt-2">
                    <div class="col-6">
                        <input
                            class="form-control bg-transparent border-info text-center"
                            type="number"
                            @input="getVal2"
                        />
                    </div>
                </div>
            </form>
        </div>
    </div>
</template>

<style scoped>
p {
    margin-bottom: 0;
}
</style>
