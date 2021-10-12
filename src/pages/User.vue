<template>
  <q-page padding class="flex column align-center q-mx-auto" style="max-width: 800px; min-width: 680px">
      <h5 class="q-my-lg">
        <strong>{{ name }}</strong> 
        님의 회원정보
      </h5>

      <q-separator />

      <div class="flex row justify-between">
        <div class="col-6">
          <UserDetail
          :email="email"
          :password="password"
          :name="name"
          :address="address"
          :phone="phone"
          :hasDog="hasDog"
          ></UserDetail>
        </div>

        <div class="col-6">
          <UserEdit
          :email="email"
          :password="password"
          :name="name"
          :address="address"
          :phone="phone"
          :hasDog="hasDog"
          @child="parents"
          ></UserEdit>
        </div>
      </div>
  </q-page>
</template>

<script>
import UserDetail from './UserDetail.vue';
import UserEdit from './UserEdit.vue';

export default {
  name: 'User',
  components: {
    UserDetail,
    UserEdit,
  },
  data() {
    return {
      email: 'meijjing@a.com',
      password: '1234',
      name: 'MK',
      address: 'Seoul',
      phone: '010-1234-1234',
      hasDog: false
    }
  },
  methods: {
    parents(user) {
      console.log(user);
      this.email = user.email;
      this.password = user.password;
      this.name = user.name;
      this.address = user.address;
      this.phone = user.phone;
      this.hasDog = user.hasDog;
    }
  }
}
</script>
