<template>
    <div class="container">
        <input :v-if="this.todos.length >= 14" type="text" class="todo-input" placeholder="Add item here" v-model="newTodo" @keyup.enter="addTodo"/>
        <!-- Add all, active, completed to filter which todos to look at -->
        <div class="item-container" v-for="todo in todos" :key="todo.id">
            <todo-item @remove-todo-item="handleRemoveTodo(todo)" v-bind:item="todo" />
        </div>
    </div>
</template>

<script>
import TodoItem from './TodoItem.vue'
export default {
  components: { TodoItem },
    name: 'todo-list',
    data() {
        return {
            newTodo: '',
            newId: 2,
            todos: [
                {
                    'id': 1,
                    'title': 'First todo item',
                    'completed': false
                }
            ]
        }
    },
    methods: {
        addTodo(){
            // If there is no text in text box then don't do anything
            if (this.newTodo.trim().length == 0)
            {
                return
            }

            // Cap the list to 14 items
            if (this.todos.length > 13)
            {
                return
            }

            // Add a todo item to the todo array
            this.todos.push({
                id: this.newId,
                title: this.newTodo,
                completed: false
            })

            this.newTodo = '';
            this.newId++;
        },

        handleRemoveTodo(todo) {
            this.todos = this.todos.filter(todoItem => todoItem.id != todo.id)
        }
    }
}
</script>

<style lang="scss">
.todo-input {
    width: 100%;
    padding: 10px 18px;
    font-size: 18px;
    margin-top: 20px;
    margin-bottom: 16px;   
    background-color: rgb(196, 250, 170);
    border-radius: 10px;
    

    &:focus {
        outline: 0;
    }
}

.item-container {
    display: flex;
    justify-content: center;
}

.container {
    margin-top: 10px;
    background-color: white;
    border-radius: 20px;
    height: 98vh;
}

.icon:hover {
    cursor: pointer;
}


</style>