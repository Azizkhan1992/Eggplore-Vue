<template>
    <div>
        <button @click="changeCount()">-</button>
        <span>{{ count }}</span>
        <button @click="changeCount(true)">+</button>
    </div>
</template>
<script>
export default {
    props: {
        value: {
            type: [Number, String],
            default: 0
        },
    },
    data() {
        return {
            count: 0
        }
    },
    mounted() {
        this.count = this.value;
    },
    methods: {
        changeCount(isInc = false) {
            if (isInc) {
                this.count++;
            } else {
                this.count--;
            }

            this.$emit('input', this.count)
        }
    }
}
</script>