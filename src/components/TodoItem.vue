<template>
    <div class="todo-item" >
        <v-checkbox v-model="item.completed" ></v-checkbox>
        <v-text-field  autofocus v-show="this.editing" ref="editfield" @keyup.enter="toggleEdit" v-model="item.title"></v-text-field>
        <div v-show="!this.editing" :class="{ completed: item.completed }" class="item-text">
            {{item.title}}
        </div>
        <div>
            <v-icon v-on:click="toggleEdit" class="icon" color="black" right>mdi-pencil</v-icon>
            <v-icon v-on:click="removeItem(item)" class="icon" color="red" right>mdi-minus-circle</v-icon>
        </div>
    </div>
</template>

<script>
export default {
    props: ['item'],
    methods: {
        removeItem(item){
            this.$emit('remove-todo-item', item)
        },
        toggleEdit() {
            this.editing = !this.editing;                
        },
        mounted(){

        }
    },
    data() {
        return {
            editing: false,
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

.v-input {
    text-align: center;
}

.item-text {
    text-align: center;
    width: 60%;
    padding-top: 10px;
    padding-bottom: 10px;
}

</style>