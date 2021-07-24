<template>
  <div class="container">
    <div class="row py-5 justify-content-center">
      <div class="col-md-10">
        <div class="card bg-light shadow text-dark">
          <div class="card-body">
            <h3 class="card-title p-5 text-center">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="30"
                height="30"
                padding="0"
                fill="currentColor"
                class="bi bi-check2-square"
                viewBox="0 0 16 16"
              >
                <path
                  d="M3 14.5A1.5 1.5 0 0 1 1.5 13V3A1.5 1.5 0 0 1 3 1.5h8a.5.5 0 0 1 0 1H3a.5.5 0 0 0-.5.5v10a.5.5 0 0 0 .5.5h10a.5.5 0 0 0 .5-.5V8a.5.5 0 0 1 1 0v5a1.5 1.5 0 0 1-1.5 1.5H3z"
                />
                <path
                  d="m8.354 10.354 7-7a.5.5 0 0 0-.708-.708L8 9.293 5.354 6.646a.5.5 0 1 0-.708.708l3 3a.5.5 0 0 0 .708 0z"
                />
              </svg>
              {{ title }}
            </h3>

            <div class="card-text">
              <label id="button-addon2" class="form-label lead"
                >What do you want to add?</label
              >
              <div class="input-group mb-3">
                <input
                  type="text"
                  v-model="task"
                  class="form-control"
                  placeholder="Task to add..."
                />
                <button
                  class="btn btn-primary btn-lg"
                  type="button"
                  id="button-addon2"
                  @click="addTask"
                >
                  Add
                </button>
              </div>

              <!-- Checkboxes -->
              <div class="row pt-5" v-for="task in tasks" :key="task.id">
                <div class="col-8">
                  <div class="form-check">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      value=""
                      id="flexCheckDefault"
                    />
                    <label class="form-check-label" for="flexCheckDefault">
                      {{ task.name }}
                    </label>
                  </div>
                </div>
                <div class="col-md-4">
                  <div class="row">
                    <div class="col-md-6">
                      <button @click="editTask(task.id)" class="btn btn-warning btn-sm px-3">Edit</button>
                    </div>
                    <div  class="col-md-6">
                      <button  @click="deleteTask(task.id)" class="btn btn-danger btn-sm">Remove</button>
                    </div>
                  </div>
                </div>
              </div>
              

              <div class="d-grid gap-2 d-md-flex justify-content-md-end pt-5">
                <button @click="clearTasks" class="btn btn-dark" type="button">Clear All</button>
              </div>
            </div>
          </div>   
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'TodoApp',
    props: {
        title: {
            type: String,
        },
    },
    data() {
        return {
            task: '',
            editedTask: null,
            tasks: [
                {
                    name: 'Doctors Appointment',
                    id: 1,

                },
                {
                    name: 'Gadites Meeting',
                    id: 2,
                },
                {
                    name: 'Online Brethren Meeting',
                    id: 3,
                }
            ],
        }
    },
    components: {
        
    },
    methods: {
        addTask() {
            if(this.task.length === 0) return;
            
            if(this.editedTask === null) {
                 this.tasks.push({
                name: this.task,
                id: Math.floor(Math.random() * 100000),
            })
            } else{
                this.tasks[this.editedTask - 1].name = this.task
                this.editedTask = null
            }
                
        

            this.task = ''
        },
        deleteTask(id) {
            this.tasks =this.tasks.filter((task) => task.id !== id)
        },
        clearTasks() {
            this.tasks = []
        },
        editTask(id) {
            this.task = this.tasks[id - 1].name
            this.editedTask = id

        },
    },
};
</script>

<style>
</style>