<template>
  <section>
    <img src="../assets/logo.svg" alt="Logo" width="200" />
    <div class="content">
      <h1 class="title">
        <span class="red-color">WE'RE</span>
        COMING SOON
      </h1>
      <p class="red-color text">
        Hello fellow shoppers! We're currently building our new fashion store.
        Add your email below to stay up-to-date with announcements and our
        launch deals.
      </p>
      <form ref="form" @submit.prevent="send">
        <div class="input__container">
          <input
            v-model="email"
            class="red-color"
            placeholder="Email Address"
            required
          />
          <!-- v-show="!valid && email" -->
          <!-- <img
              src="../assets/icon-error.svg"
              alt="Error"
              class="error-icon"
            /> -->
          <button class="submit-btn" @click="validate()">
            <img src="../assets/icon-arrow.svg" />
          </button>
        </div>
        <h3 :class="`message ${valid ? 'success' : 'error'}`">
          {{ message }}
        </h3>
      </form>
    </div>
  </section>
  <img src="../assets/hero-desktop.jpg" alt="Hero" class="hero-img" />
</template>
  
<script>
export default {
  name: "HomePageDesktop",
  data: () => ({
    email: "",
    valid: false,
    message: "",
  }),
  watch: {
    email: "validate",
  },
  methods: {
    validate() {
      if (this.email) {
        const isValid = /.+@.+\..+/.test(this.email);
        this.valid = isValid;

        if (isValid) {
          this.message = "";
        } else {
          this.message = "Please provide a valid email";
        }
      } else {
        this.message = "E-mail is required";
      }
    },
    send() {
      console.log(this.valid);
      if (this.valid) {
        this.message = "Email Sent !";
      }
    },
  },
};
</script>
  
<style lang="css">
input {
  box-sizing: border-box;
  font-size: 18px;
  width: 100%;
  height: 100%;
  padding: 0px 20px;
  padding-right: 100px;
  border-radius: 5rem;
  outline: none;
}

.input__container {
  height: 56px;
  position: relative;
}

button {
  outline: none;
  border: none;
  cursor: pointer;
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  right: -1px;
  width: 95px;
  height: 60px;
  border-radius: 5rem;
  background: linear-gradient(hsl(0, 80%, 86%), hsl(0, 74%, 74%));
}

section {
  max-width: 450px;
}

.hero-img {
  height: 100vh;
}

.input__container {
  display: flex;
}

.error-icon {
  width: 20px;
  height: 20px;
  position: relative;
  left: -8vh;
  top: 2vh;
}

section {
  padding: 3rem 25vh 0 25vh;
}

.content {
  padding-top: 10vh;
}

p {
  font-size: 1.1rem;
  margin-top: 2rem;
  margin-bottom: 2.5rem;
  line-height: 1.5rem;
}

h1 {
  font-weight: lighter;
  letter-spacing: 1.5rem;
  line-height: 4.5rem;
}

.title {
  font-size: 64px;
  font-weight: 100;
  letter-spacing: 24px;
  line-height: 72px;
}

.text {
  font-size: 18px;
  line-height: 24px;
  margin: 40px 0px;
}

.error {
  color: red;
}

.success {
  color: green;
}
</style>