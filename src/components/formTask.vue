<template>
    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Form to create new task">
                <input type="text" class="input" placeholder="Qual tarefa você deseja iniciar?" />
            </div>
            <div class="column">
                <TimerWatch/>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import TimerWatch from './timer.vue';
export default defineComponent({
    name:'FormTask',
    components:{
        TimerWatch
    }
})
</script>