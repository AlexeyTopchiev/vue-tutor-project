<template>
    <div>
        <h1>Счётчик: {{ counter }}</h1>
    </div>
</template>

<script>
import {eventEmitter} from '../main.js'
export default {
    data() {
        return {
            counter: 0
        }
    },
    created() {
        eventEmitter.$on('counterUpdated', () => {
            this.counter++
        })
    }
}
</script>

