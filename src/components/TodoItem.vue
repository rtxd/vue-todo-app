<template>
    <div class="todo-item" >
        <v-checkbox v-model="item.completed" ></v-checkbox>
        <input v-if="this.editing" />
        <div v-else :class="{ completed: item.completed }">
            {{this.title}}
        </div>
        <!-- TODO: Add edit icon with edit functionality -->
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
    },
    data() {
        return {
            editing: true,
            title: this.item.title,
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
    background-color: #fbfafa;
    width: 50vw;
}

.completed {
    text-decoration: line-through;
    font-style: italic;
    color: rgb(107, 107, 107);
}

</style>