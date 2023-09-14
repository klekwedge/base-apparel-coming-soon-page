<template>
  <div class="homepage-desktop">
    <section>
      <img src="../assets/logo.svg" alt="Logo" width="200" />

      <div class="content">
        <h1 class="large-text">
          <span class="red-color">WE'RE</span>
          COMING SOON
        </h1>
        <p class="red-color">
          Hello fellow shoppers! We're currently building our new fashion store.
          Add your email below to stay up-to-date with announcements and our
          launch deals.
        </p>
        <form ref="form">
          <div class="input-div">
            <input
              v-model="email"
              :rules="[rules.required, rules.email]"
              class="red-color"
              label="Email Address"
              :success-messages="valid && emailSent ? 'Email Sent !' : ''"
              required
            />
            <img
              v-show="!valid && email"
              src="../assets/icon-error.svg"
              alt="Error"
              class="error-icon"
            />
            <button class="submit-btn" @click="validate()">
              <img src="../assets/icon-arrow.svg" />
            </button>
          </div>
        </form>
      </div>
    </section>
    <img
      src="../assets/hero-desktop.jpg"
      alt="Hero"
      width="50%"
      class="hero-img"
    />
    <!-- :position="$vuetify.breakpoint.mdAndDown ? 'center top' : 'left top'" -->
  </div>
</template>
  
  <script>
export default {
  name: "HomePageDesktop",
  data() {
    return {
      email: "",
      valid: true,
      emailSent: false,
      rules: {
        required: (value) => !!value || "E-mail is required",
        email: (value) =>
          /.+@.+\..+/.test(value) || "Please provide a valid email",
      },
    };
  },
  methods: {
    validate() {
      this.$refs.form.validate();
      if (this.valid) this.emailSent = true;
    },
  },
};
</script>
  
<style lang="css">
.homepage-desktop {
  display: flex;
  flex-direction: row !important;
  font-family: "Josefin Sans";
  height: 100vh;
}

.homepage-desktop .input-div {
  display: flex;
}

.homepage-desktop .error-icon {
  width: 20px !important;
  height: 20px !important;
  position: relative;
  left: -8vh;
  top: 2vh;
}

.homepage-desktop .submit-btn {
  left: -7vh;
  width: 95px !important;
  height: 60px !important;
  border-radius: 5rem !important;
  background: linear-gradient(hsl(0, 80%, 86%), hsl(0, 74%, 74%)) !important;
}

.homepage-desktop section {
  padding: 3rem 25vh 0 25vh;
}

.homepage-desktop .content {
  padding-top: 10vh;
  /* height: 100vh; */
}

.homepage-desktop p {
  font-size: 1.1rem;
  margin-top: 2rem;
  margin-bottom: 2.5rem;
  line-height: 1.5rem;
}

.homepage-desktop h1 {
  font-weight: lighter;
  letter-spacing: 1.5rem;
  line-height: 4.5rem;
}

.homepage-desktop .large-text {
  font-size: 4rem;
}

@media screen and (max-width: 1400px) {
  .homepage-desktop section {
    padding: 1rem;
  }
}
</style>