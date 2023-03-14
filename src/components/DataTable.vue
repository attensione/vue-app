<template>

    <div class="input-group mb-3">
      <button class="btn btn-outline-secondary" type="button" data-bs-toggle="modal" data-bs-target="#addDataModal">Add Data</button>
      <button class="btn btn-outline-secondary" type="button" data-bs-toggle="modal" data-bs-target="#addCategoryModal">Add Category</button>
      <input type="text" class="form-control" placeholder="Search data" aria-label="Example text with two button addons">
    </div>

  <table class="table">
    <thead>
      <tr>
        <th scope="col"><a href="#">#</a></th>
        <th scope="col"><a href="#">mount</a></th>
        <th scope="col"><a href="#">spec</a></th>
        <th scope="col"><a href="#">price</a></th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="house in houses" :key="house.id">
        <th scope="row">{{ house.id }}</th>
        <td>{{ house.mount }}</td>
        <td>{{ house.spec }}</td>
        <td>{{ house.price }} zł</td>
      </tr>
    </tbody>
  </table>

  <div class="modal fade" id="addDataModal" tabindex="-1" aria-labelledby="addDataModalLabel" aria-hidden="true">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h1 class="modal-title fs-5" id="exampleModalLabel">Add New Data</h1>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body">
          ...
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
          <button type="button" class="btn btn-primary">Save changes</button>
        </div>
      </div>
    </div>
  </div>

  <div class="modal fade" id="addCategoryModal" tabindex="-1" aria-labelledby="addCategoryModalLabel" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h1 class="modal-title fs-5" id="exampleModalLabel">Add New Category</h1>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body">
            ...
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
            <button type="button" class="btn btn-primary">Save changes</button>
          </div>
        </div>
      </div>
    </div>

</template>



<script>
export default {
  name: 'DataTable',
  props: ['houses']
}
</script>