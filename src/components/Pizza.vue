<template>
    <div>
        <h1>Pizza Name: {{ pizzaName }} / {{ reverseName }}</h1>
        <h2>Price: {{ pizzaPrice }} </h2>
        <button @click="changeName">Change Name</button>
        <button @click="changeFunc()">Change Name from Parent</button>

    </div>
</template>

<script>
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
            this.$emit('changedName', this.pizzaName)
        }
    },
    computed: {
        reverseName () {
            return this.pizzaName.split('').reverse().join('')
        }
    }
}
</script>

