<script>
    export default{
        data() {
            return {
                items: [
                    { name: "Study Vue", complete: false},
                    { name: "Sleep", complete: false}
                ],
                addedItem: ""
            } 
        },
        methods:{
            addItem(){
                this.items.push({ name: this.addedItem, complete: false })
            }
        }
    }
</script>
<template>
    <div class="mx-5">
        <h1 class="text-2xl">Todo List</h1><br>
        <input type="text" placeholder="Enter Item" v-model="addedItem" class="shadow appearance-none border rounded py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
        <button @click="addItem" class="ml-2 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 border border-blue-700 rounded">Add</button>
        <ul class="">
            <li v-for="item in items" class="">
                <label for="" :class= " item.complete ? 'completed': 'pending' ">
                    {{ item.name }}
                </label>
                <input type="checkbox" v-model="item.complete" :key="item.name">
            </li>
        </ul>
    </div>
</template>
<style>
    .completed{
        text-decoration: line-through;
    }
</style>