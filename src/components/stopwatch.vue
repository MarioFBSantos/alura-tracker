<template>
    <section>
        <strong>
            {{formatTime}}
        </strong>
    </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name:'StopWatch',
    props:{
        seconds: {
            type: Number,
            default: 0
        }
    },
    computed:{
        formatTime(): string{
            return new Date(this.seconds * 1000).toISOString().substr(11,8);
        }
    },
})
</script>

<style scoped>
</style>