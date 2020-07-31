<template>
  <div id="app">
    <div class="container" id="register-form" v-if="!isSubmited">
      <div class="register-header">
        <h1>Регистрация нового клиента</h1>
        <hr />
      </div>
      <form class="client-form" @submit.prevent="isSubmited = true">
        <user-form />
        <address-form />
        <passport-form />
        <button class="btn" type="submit">Регистрация</button>
      </form>
    </div>
    <div v-else class="container" id="submitSuccess">
      <h1>Регистрация прошла успешно</h1>
      <pre></pre>
    </div>
  </div>
</template>

<script>
import UserForm from "@/components/UserForm";
import AddressForm from "@/components/AddressForm";
import PassportForm from "@/components/PassportForm";
export default {
  name: "App",
  data: () => ({
    isSubmited: false,
  }),
  components: {
    UserForm,
    AddressForm,
    PassportForm,
  },
};
</script>

<style lang="scss">
@import "./assets/mixins.scss";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
#register-form {
  border: 1px solid black;
  border-radius: 5px;
}
#submitSuccess {
  text-align: center;
}
.container {
  @include container(960px);
}
.register-header h1 {
  @include container(720px);
  padding: 1.5rem;
}
.client-form {
  @include container(720px);
  display: flex;
  flex-flow: column nowrap;
  padding: 0 1rem;
}

.btn {
  padding: 0.5rem 2rem;
  margin-left: auto;
  margin-bottom: 4rem;
  margin-top: 2rem;
}

.form-group {
  display: flex;
  flex-flow: column nowrap;

  margin-bottom: 1rem;

  label {
    margin-bottom: 0.25rem;
  }

  input[type="text"],
  input[type="date"],
  input[type="tel"],
  select {
    height: 1.5rem;
  }

  select[multiple] {
    height: auto;
  }
}

@media screen and(max-width: 768px) {
  #register-form {
    border: 0;
  }
}
</style>
