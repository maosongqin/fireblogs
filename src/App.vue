<template>
  <messageInput v-if="state1" @inputMessage="getChildMessage"></messageInput>
  <passcard v-if="state2" :name="name" :id="id"></passcard>
</template>


<script>
import messageInput from "./components/input.vue";
import passcard from "./components/passcard.vue";
export default {
  name: "App",
  components: {
    messageInput,
    passcard,
  },
  data() {
    return {
      name: "",
      id: "",
      state1: true,
      state2: false,
    };
  },
  methods: {
    getChildMessage(name, id) {
      this.name = name;
      this.id = id;
      this.state1 = false;
      this.state2 = true;
    },
  },
};
</script>
