<script>
    // TODO: Complete the code
    export default { 
        data() {
            return {
                
            }
        },
        // Hint: insert properties task (Object) and idx (Number)
        props:{
            task: Object,
            idx: Number,
        }
    }
</script>

<template>
    <!-- TODO: add your template code here --> 
   <div class="card " style="width: 18rem;">
        <div class="card-body">
            <h5 class="card-title fw-semibold">Deadline: {{ task.deadline }}</h5>
            <hr>
            <p class="card-text">{{ task.desc }}</p>
            <button class="btn btn-primary" @click="$emit('delete', idx)">Done</button>
        </div>
    </div>
</template>


