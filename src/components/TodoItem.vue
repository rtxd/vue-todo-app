<template>
    <div class="todo-item" :bind="{ 'is-selected': 'item.completed' }">
        <v-checkbox v-model="item.completed" ></v-checkbox>
        {{item.title}}
        <v-icon v-on:click="removeItem(item)" class="icon" color="red" right>mdi-minus-circle</v-icon>
    </div>
</template>

<script>
export default {
    props: ['item'],
    methods: {
        removeItem(item){
            this.$emit('remove-todo-item', item)
        }
    }
};
</script>

<style>
.todo-item {
    display: flex;
    justify-content: space-between;
    border: solid 1px;
    padding-top: 0px;
    padding-left: 10px;
    padding-right: 10px;
    border-radius: 10px;
    margin-top: 20px;
    align-items: center;
    background-color: cornsilk;
    width: 50vw;
}

.is-selected label {
    text-decoration: line-through;
}
</style>