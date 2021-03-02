<template>
    <div>
        <input type="text" class="todo-input" placeholder="Add item here" v-model="newTodo" @keyup.enter="addTodo"/>
        <div v-for="todo in todos" :key="todo.id" class="todo-item">
            {{todo.title}}
            <button>x</button>
        </div>
    </div>
</template>

<script>
export default {
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
            if (this.newTodo.trim().length == 0)
            {
                return
            }

            this.todos.push({
                id: this.newId,
                title: this.newTodo,
                completed: false
            })

            this.newTodo = '';
            this.newId++;
        }
    }
}
</script>

<style lang="scss">
.todo-input {
    width: 100%;
    padding: 10px 18px;
    font-size: 18px;
    margin-bottom: 16px;   
}

.todo-item {
    display: flex;
    justify-content: space-between;
    border: solid 1px;
    padding: 10px;
}
</style>