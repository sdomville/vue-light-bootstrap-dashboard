<template>
  <div class="content">
    <div class="container-fluid">
      <div class="row">
        <!-- <div class="col-12">
          <card class="strpied-tabled-with-hover"
                body-classes="table-full-width table-responsive"
          >
            <template slot="header">
              <h4 class="card-title">Striped Table with Hover</h4>
              <p class="card-category">Here is a subtitle for this table</p>
            </template>
            <l-table class="table-hover table-striped"
                     :columns="table1.columns"
                     :data="table1.data">
            </l-table>
          </card>

        </div> -->

        <!-- <div class="col-12">
          <card class="card-plain">
            <template slot="header">
              <h4 class="card-title">Table on Plain Background</h4>
              <p class="card-category">Here is a subtitle for this table</p>
            </template>
            <div class="table-responsive">
              <l-table class="table-hover"
                       :columns="table2.columns"
                       :data="table2.data">
              </l-table>
            </div>
          </card>
        </div> 

        <div class="col-12">
          <card class="strpied-tabled-with-hover"
                body-classes="table-full-width table-responsive"
          >
            <template slot="header">
              <h4 class="card-title">Events CRUD</h4>
              <p class="card-category">Add and Delete Events</p>
            </template>
            <l-table class="table-hover table-striped table-sm"
                     :columns="table1.columns"
                     :data="table1.data">
            </l-table>
          </card>

        </div> -->



      <template>
        <div>
          <button class="btn btn-success float-right" @click="openModal">Open Modal</button>
          <ModalComponent :is-visible="isModalVisible" @close="closeModal">
            <!-- <p>This is the modal content.</p> -->
            <div class="content">
              <edit-profile-form>
              </edit-profile-form>
            </div>
          </ModalComponent>
        </div>
      </template>

              
      <!-- <card class="col-md-6"> AN OPTION.... -->
      <card class="strpied-tabled-with-hover col-md-12"
                body-classes="table-full-width table-responsive"
          >
        <template slot="header">
          <div class="cardheader">
          <h4 class="card-title">Events CRUD</h4>
          </div>
          <div class="cardbtn">
            <!-- <div class="text-center"> -->
            <button type="submit"  class="btn btn-success float-right">
              Add
            </button>
          </div>
            <!-- </div> -->
          <!-- <p class="card-category">Add and Delete Events</p> -->
        </template>
        <l-table class="table-hover table-striped table-sm"
                  :columns="table1.columns"
                  :data="table1.data">
        </l-table>
      </card>
      <!-- </card> -->





      </div>
    </div>
  </div>
</template>
<script>
  import LTable from 'src/components/Table.vue'
  import Card from 'src/components/Cards/Card.vue'
  import ModalComponent from 'src/components/ModalComponent.vue';
  import EditProfileForm from './UserProfile/EditProfileForm.vue'
  import UserCard from './UserProfile/UserCard.vue'

  const tableColumns = ['Id', 'Name', 'Salary', 'Country', 'City']
  const tableData = [{
    id: 1,
    name: 'Dakota Rice',
    salary: '$36.738',
    country: 'Niger',
    city: 'Oud-Turnhout'
  },
  {
    id: 2,
    name: 'Minerva Hooper',
    salary: '$23,789',
    country: 'Curaçao',
    city: 'Sinaai-Waas'
  },
  {
    id: 3,
    name: 'Sage Rodriguez',
    salary: '$56,142',
    country: 'Netherlands',
    city: 'Baileux'
  },
  {
    id: 4,
    name: 'Philip Chaney',
    salary: '$38,735',
    country: 'Korea, South',
    city: 'Overland Park'
  },
  {
    id: 5,
    name: 'Doris Greene',
    salary: '$63,542',
    country: 'Malawi',
    city: 'Feldkirchen in Kärnten'
  }]
  export default {
    components: {
      LTable,
      Card,
      ModalComponent,
      EditProfileForm,
      UserCard
    },
    data () {
      return {
         isModalVisible: false,
        table1: {
          columns: [...tableColumns],
          data: [...tableData]
        },
        table2: {
          columns: [...tableColumns],
          data: [...tableData]
        }
      }
    },
    methods: {
    openModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.isModalVisible = false;
    },
    },
  }
</script>
<style>
</style>
