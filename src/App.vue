<template>
  <div
    className=" mx-auto container h-screen w-full flex flex-col p-6 justify-center items-center  bg-purple-900"
  >
    <h1 class="text-3xl text-red-900 font-bold underline">Hello world!</h1>
    <user-data @new-data="newData"></user-data>
    <active-user
      v-for="user in users"
      :key="user.id"
      :id="user.id"
      :name="user.name"
      :age="user.age"
    ></active-user>
  </div>
</template>

<script>
import ActiveUser from './components/ActiveUser.vue'
import UserData from './components/UserData.vue'
export default {
  components: { ActiveUser, UserData },
  data() {
    return {
      users: [
        {
          id: 1,
          name: 'oladapo',
          age: 23,
        },
        {
          id: 2,
          name: 'adejoro',
          age: 34,
        },
      ],
    }
  },

  methods: {
    newData(name, age) {
      const newUser = {
        id: new Date().getUTCMilliseconds(),
        name: name,
        age: age,
      }
      this.users.push(newUser)
    },
  },
}
</script>
