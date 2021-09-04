<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld :msg="`${greeting} ${user.name}`" />
    <button @click="changeGreeting">Greet Again</button>
  </div>
</template>

<script>
import { reactive, ref } from "@vue/reactivity";
import HelloWorld from "@/components/HelloWorld";

export default {
  name: "Home",
  components: {
    HelloWorld,
  },
  setup() {
    const data = {
      greeting: ref(`Welcome to Your Vue.js App`),
      user: reactive({
        name: "John Doe",
        email: "john@doe.me",
      }),
    };

    const methods = {
      changeGreeting: () => {
        data.greeting.value = `Welcome again`;
      },
    };

    return {
      ...data,
      ...methods,
    };
  },
};
</script>
