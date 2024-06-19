<template>
  <section
    className=" bg-yellow-600 border flex flex-col p-6 justify-center rounded-lg w-1/3 mb-6"
  >
    <form
      class="flex flex-col justify-center gap-2"
      @submit.prevent="submitUser"
    >
      <div
        className="flex flex-row  w-full justify-around font-semibold items-center align-middle"
      >
        <label>name</label>
        <input type="text" class="rounded-xl p-1" v-model="enteredName" />
      </div>
      <div
        className="flex flex-row  w-full justify-around font-semibold items-center align-middle"
      >
        <label>age</label>
        <input type="text" class="rounded-xl p-1" v-model="enteredAge" />
      </div>

      <div class="flex flex-row justify-center">
        <button class="border-2 bg-slate-500 text-white px-5 py-3 rounded-lg">
          add
        </button>
      </div>
    </form>
  </section>
</template>

<script>
export default {
  emits: ['new-data'],
  data() {
    return {
      enteredName: '',
      enteredAge: '',
    }
  },

  methods: {
    submitUser() {
      this.$emit('new-data', this.enteredName, this.enteredAge)
    },
  },
}
</script>
