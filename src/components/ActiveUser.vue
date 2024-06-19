<template>
  <section
    className=" bg-yellow-600 border mb-3 flex flex-col p-6 justify-center rounded-lg w-1/3"
  >
    <div class="">
      <h2 className=" text-xl text-white">My name : {{ name }}</h2>
      <h3 className=" text-lg ext-white">My age : {{ age }}</h3>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    id: {
      type: Number,
      required: true,
    },

    name: {
      type: String,
      required: true,
    },
    age: {
      type: Number,
      required: true,
    },
  },
  data() {
    return {}
  },
}
</script>
