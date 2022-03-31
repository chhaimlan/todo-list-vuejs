<template>
<div>
    <div class="container">
        <br>
        <h1 class="text-center">Todo App</h1>
        <br>
        <form @submit="addTodo">
            <div class="form-group">
                <input type="text" v-model="title" placeholder="Title" required class="form-control" />
            </div>
            <div class="form-group">
                <button class="btn btn-danger btn-block">
                    AddTodo
                </button>
            </div>
        </form>        
    </div>
</div>
</template>

<script>
export default {
    name:'Apptodo',
    data(){
        return {
            title:''
        }
    },
    methods:{
        addTodo(e){
            e.preventDefault();           
            const newTodo = {
                id:Date.now(),
                title:this.title,
                completed: false,
            }
            //send out event

            this.$emit('add-todo',newTodo);

            //clear input fild
            this.title = ""
        }
    }
}
</script>
<style scoped>

</style>