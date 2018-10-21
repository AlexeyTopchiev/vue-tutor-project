<template>
    <div>
        <h1>Pizza Name: {{ pizzaName }} / {{ reverseName }}</h1>
        <h2>Price: {{ pizzaPrice }} </h2>
        <button @click="changeName">Change Name</button>
        <button @click="changeFunc()">Change Name from Parent</button>
        <button @click="updateCounter">Update Counter</button>

    </div>
</template>

<script>
import {eventEmitter} from '../main.js'
export default {
    name: 'pizza',
    props: ['pizzaName', 'pizzaPrice', 'changeFunc'],
    // props: {
    //     pizzaName: String,
    //     pizzaPrice: Number
    // },
    // props: {
    //     pizzaName: {
    //         type: String,
    //         required: true,
    //         default: "Default Pizza Name"
    //     },
    //     pizzaPrice: {
    //         type: Number
    //     }
    // },
    methods: {
        changeName () {
            this.pizzaName = 'Маргарита'
            this.$emit('nameChanged', this.pizzaName)
        },
        updateCounter() {
            eventEmitter.$emit('counterUpdated')
        }
    },
    computed: {
        reverseName () {
            return this.pizzaName.split('').reverse().join('')
        }
    }
}
</script>

