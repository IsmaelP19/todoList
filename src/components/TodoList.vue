<template>
    <div>
        <input class="inputTodo" type="text" v-model="newTodoText"/>
        <button v-on:click="addTodo">Add task</button>
        <hr>

        <ul>
            <div class="todo" v-for="todo in todos" :key="todo">
                <li>
                    {{ todo.text }}
                </li>
                <button v-on:click="removeTask(todo.id)">Delete</button>
            </div>           
        </ul>
    </div>
</template>

<script>
let nextTodoId = 1;


export default {
    name: 'TodoList',
    components: {
        
    }, 
    data() {
        return {
            todos: [
                {id: nextTodoId++, text: 'Learn Vue'},
                {id: nextTodoId++, text: 'Finish course'},
                {id: nextTodoId++, text: 'Do the exam'},
            ]
        }
    },
    
    methods: {
        addTodo: function() {
            if(this.newTodoText) {
                const trimmedText = this.newTodoText.trim()

                if(trimmedText) {
                    this.todos.push({
                        id: nextTodoId++,
                        text: trimmedText
                    })
                    
                }

                this.newTodoText = ''

                
            }
        },
        removeTask(idToRemove) {
            this.todos = this.todos.filter(todo => todo.id !== idToRemove)
        }
    }
}
</script>


<style scoped>
.todo {
    display: flex;
    justify-content: center;
    padding: 8px;

}

.todo li {
    font-size: 24px;
}

.inputTodo {
    padding: 10px;
    font-size: 32px;
    width: 30%;
}

</style>