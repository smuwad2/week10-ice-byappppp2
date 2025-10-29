<script>
    import TaskTracker from './subcomponents/TaskTracker.vue';

    export default {
        data() {
            return {
                desc: '',
                deadline: '',
                taskList: []
            }
        },
        methods: {
            add() {
                this.taskList.push( { 'desc': this.desc, 'deadline': this.deadline } )
                this.desc = ''
                this.deadline = ''
                console.log(this.taskList);
            },
            // TODO: Add a new method, to delete a task completed
            deleteCard(id){
                this.taskList.splice(id, 1)
            }
        },
        components:{
            TaskTracker,
        }
    }

</script>

<template>
    <div class="mb-3">
        <label for="desc" class="form-label">Task</label>
        <input type="text" class="form-control" id="desc" v-model='desc' placeholder="task">
    </div>
    <div class="mb-3">
        <label for="deadline" class="form-label">Deadline</label>
        <input type="date" class="form-control" id="deadline" v-model='deadline' placeholder="deadline">
    </div>

    <button type="button" @click="add" class="btn btn-primary">Add New Task</button>
    <hr>

    <!-- TODO: Modify following code -->
    <div class="d-flex flex-row">
        <task-tracker
            v-for="(task, idx) in taskList"
            :key="idx"
            :task="task"
            v-on:delete="deleteCard(idx)"
        ></task-tracker>
    </div>

</template>

<style scoped>
   
</style>
