<template>
    <div class="py-4">
        <div class="container">
            <div class="title border-bottom d-flex align-items-center justify-content-between py-2">
                <h5>Task</h5>
                <div class="d-flex align-items-center">
                    <span class="me-2">View As</span>
                    <button
                        class="btn btn-outline-secondary py-1 px-3"
                        @click="isGrid = !isGrid"
                    >
                        {{ isGrid ? 'Grid' : 'List' }}
                    </button>
                </div>
            </div>
            <div class="list-task row">
                <CardItem :task="tasks[0]" :isGrid="isGrid" />
                <CardItem :task="tasks[1]" :isGrid="isGrid" />
                <CardItem :task="tasks[2]" :isGrid="isGrid" />
            </div>
            <div class="action py-2">
                <a
                    href="!#"
                    class="add-button"
                    v-if="!isCreating"
                    @click.prevent="isCreating = !isCreating"
                >
                    Add Task
                </a>
                <div class="add-card" v-else>
                    <div class="card mb-2">
                        <div class="card-body d-flex flex-column p-0">
                            <input class="form-control border-0 mb-2" placeholder="Title" type="text">
                            <textarea class="form-control border-0 small" placeholder="Description"
                            rows="3"></textarea>
                        </div>
                    </div>
                    <div class="button-wrapper d-flex">
                        <button class="btn btn-primary me-2">Save</button>
                        <button class="btn btn-outline-secondary" @click="isCreating = !isCreating">Cancel</button>
                    </div>
                </div>
            </div>>
        </div>
    </div>
</template>

<script>

import CardItem from "@/components/Card/CardItem.vue"

export default {
    components:{
        CardItem
    },
    data() {
        return {
            tasks: [
                {
                    title: 'Task 1',
                    description: 'ini deskripsi',
                    isDone: false,
                },
                {
                    title: 'Task 2',
                    description: 'ini deskripsi 2',
                    isDone: false,
                },
                {
                    title: 'Task 3',
                    description: ' ini deskripsi 3',
                    isDone: false,
                }
            ],
            isCreating:false,
            isGrid: false,
        }
    }
}
</script>
