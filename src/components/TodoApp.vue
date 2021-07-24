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
              ToDo App
            </h3>

            <div class="card-text">
              <label id="button-addon2" class="form-label lead"
                >What do you want to add?</label
              >
              <div class="input-group mb-3">
                <input
                  type="text"
                  class="form-control"
                  placeholder="Task to add..."
                />
                <button
                  class="btn btn-primary btn-lg"
                  type="button"
                  id="button-addon2"
                >
                  Add
                </button>
              </div>

              <!-- Checkboxes -->
              <div class="row pt-5">
                <div class="col-8">
                  <div class="form-check">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      value=""
                      id="flexCheckDefault"
                    />
                    <label class="form-check-label" for="flexCheckDefault">
                      Task 1
                    </label>
                  </div>
                </div>
                <div class="col-md-4">
                  <div class="row">
                    <div class="col-md-6">
                      <button class="btn btn-warning btn-sm px-3">Edit</button>
                    </div>
                    <div class="col-md-6">
                      <button class="btn btn-danger btn-sm">Remove</button>
                    </div>
                  </div>
                </div>
              </div>
              <div class="row pt-5">
                <div class="col-8">
                  <div class="form-check">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      value=""
                      id="flexCheckDefault"
                    />
                    <label class="form-check-label" for="flexCheckDefault">
                      Task 2
                    </label>
                  </div>
                </div>
                <div class="col-md-4">
                  <div class="row">
                    <div class="col-md-6">
                      <button class="btn btn-warning btn-md">Edit</button>
                    </div>
                    <div class="col-md-6">
                      <button class="btn btn-danger btn-md">Remove</button>
                    </div>
                  </div>
                </div>
              </div>

              <div class="d-grid gap-2 d-md-flex justify-content-md-end pt-5">
                <button class="btn btn-dark" type="button">Clear All</button>
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
    data() {
        return {
            tasks: [
                {
                    name: 'Doctors Appointment',

                }
            ],
        }
    },
    components: {
        
    },
};
</script>

<style>
</style>