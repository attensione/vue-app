<template>
    <div class="alert alert-success d-none" role="alert">
      A simple success alert—check it out!
    </div>

    <div class="input-group mb-3">
      <button class="btn btn-outline-secondary" type="button" data-bs-toggle="modal" data-bs-target="#addDataModal">Add Data</button>
      <button class="btn btn-outline-secondary" type="button" data-bs-toggle="modal" data-bs-target="#addCategoryModal">Add Category</button>
      <input type="text" class="form-control" placeholder="Search data" aria-label="Input for search data" @input="housesSearch" />
      <button class="btn btn-outline-secondary" type="button" data-bs-toggle="modal" data-bs-target="#changeCurrencyModal">Change Currency</button>
    </div>

  <table class="table">
    <thead>
      <tr>
        <th scope="col"><a href="#" @click="housesSort('id')">#</a></th>
        <th scope="col"><a href="#" @click="housesSort('mount')">mount</a></th>
        <th scope="col"><a href="#" @click="housesSort('spec')">spec</a></th>
        <th scope="col"><a href="#" @click="housesSort('price')">price</a></th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="house in newHouses" :key="house.id">
        <th scope="row">{{ house.id }}</th>
        <td>{{ house.mount }}</td>
        <td>{{ house.spec }}</td>
        <td>{{ house.price }} zł</td>
      </tr>
    </tbody>
  </table>

  <div class="modal fade" id="addDataModal" tabindex="-1" aria-labelledby="addDataModalLabel" aria-hidden="true">
    <div class="modal-dialog">
      <form class="modal-content" @submit.prevent="addData">
        <div class="modal-header">
          <h1 class="modal-title fs-5" id="addDataModalLabel">Add New Data</h1>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body text-start">
              <div class="mb-3">
                  <select name="dataMount" id="dataMount" class="form-select" aria-label="Default select example">
                        <option value=false disabled selected>Choose Data Mount</option>
                      <option v-for="(mount, i) in newMounts" :key="i">{{ mount }}</option>
                  </select>
              </div>
              <div class="mb-3">
                    <select name="dataSpec" id="dataSpec" class="form-select" aria-label="Default select example">
                        <option value=false disabled selected>Choose Data Spec</option>
                        <option v-for="(spec, i) in newSpecs" :key="i">{{ spec }}</option>
                    </select>
              </div>
              <div class="mb-3">
                    <input type="text" class="form-control" name="dataPrice" id="dataPrice" placeholder="Data Price">
             </div>
             <div class="mb-3">
                  <div id="dataFeedback" class="form-text alert alert-danger d-none" role="alert">feedback is null</div>
             </div>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
          <button type="submit" class="btn btn-primary">Add Data</button>
        </div>
      </form>
    </div>
  </div>

  <div class="modal fade" id="addCategoryModal" tabindex="-1" aria-labelledby="addCategoryModalLabel" aria-hidden="true">
      <div class="modal-dialog">
        <form class="modal-content" @submit.prevent="addCategory">
          <div class="modal-header">
            <h1 class="modal-title fs-5" id="addCategoryModalLabel">Add New Category</h1>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body text-start">
                <div class="mb-3">
                    <select name="categoryType" id="categoryType" class="form-select" aria-label="Default select example">
                        <option value=false disabled selected>Choose Category Type</option>
                        <option value="mount">mount</option>
                        <option value="spec">spec</option>
                    </select>
                </div>
                <div class="mb-3">
                 <input type="text" class="form-control" name="categoryInput" id="categoryInput" placeholder="Category Name">
               </div>
               <div class="mb-3">
                    <div id="categoryFeedback" class="form-text alert alert-danger d-none" role="alert">feedback is null</div>
               </div>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
            <button type="submit" class="btn btn-primary">Add Category</button>
          </div>
        </form>
      </div>
    </div>

    <div class="modal fade" id="changeCurrencyModal" tabindex="-1" aria-labelledby="changeCurrencyModalLabel" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h1 class="modal-title fs-5" id="changeCurrencyModalLabel">Change Currency</h1>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body">
            <select class="form-select" aria-label="Default select example" @change="changeCurrency">
                <option value=false disabled selected>Choose Default Currency</option>
                <option value="zł">zł</option>
                <option value="eur">euro</option>
                <option value="dol">dolar</option>
            </select>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
          </div>
        </div>
      </div>
    </div>

</template>



<script>
export default {
  name: 'DataTable',
  props: ['houses', 'mounts', 'specs'],
  data () {
    return {
        currency: null,
       newHouses: { ...this.houses },
       newMounts: { ...this.mounts },
       newSpecs: { ...this.specs },
    }
  },
  methods: {
    housesSort(col) {
        console.log(col);
        console.log(this.newHouses);
    },
    housesSearch(e) {
        console.log(e.target.value);
    },
    changeCurrency(e) {
        console.log(e.target.value);
    },
    addData(e) {
        e.preventDefault();
        console.log(e.target.dataMount.value);
    },
    addCategory(e) {
        e.preventDefault();
        console.log(e.target.value);
    },
  }
}
</script>