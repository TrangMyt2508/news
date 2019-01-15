<template>
  <div class="component">
    <p>Ten toi la {{ name }}</p>
    <p>Toi nam nay {{ age }} tuoi</p>

    <div class="row">
      <!--<div class="col-xs-12 col-sm-6 col-6">-->
        <!--<app-user-detail v-bind:age="age"></app-user-detail>-->
      <!--</div>-->
      <button @click="resetAge">Reset tuoi</button>
      <hr>
      <app-user-detail :age="age" @ageWasUpdated="age = $event"></app-user-detail>
      <hr>
      <div class="col-xs-12 col-sm-6 col-6">
        <app-user-edit :user-age="age" @ageWasEdited="age = $event"></app-user-edit>
      </div>
    </div>
  </div>
</template>

<script>
import UserDetail from './UserDetails.vue'
import EditUser from './EditUser.vue'
export default {
  data: function () {
    return {
      name: 'Duy',
      age: 23
    }
  },
  components: {
    appUserDetail: UserDetail,
    appUserEdit: EditUser
  },
  methods: {
    resetAge () {
      this.age = 29
    }
  }
}
</script>
<style>
  .component{
    background-color:aqua;
    text-align: left;
    width: 500px;

  }

</style>
