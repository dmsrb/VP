<template>
  <div>
    <b-form
      v-if="show"
      @submit="onSubmit"
      @reset="onReset"
    >
      <b-form-group
        id="input-group-1"
        label="Email address:"
        label-for="input-1"
        description="We'll never share your email with anyone else."
      >
        <b-form-input
          id="input-1"
          v-model="form.email"
          type="email"
          placeholder="Enter email"
          required
        />
      </b-form-group>

      <b-form-group
        id="input-group-2"
        label="Your Name:"
        label-for="input-2"
      >
        <b-form-input
          id="input-2"
          v-model="form.name"
          placeholder="Enter name"
          required
        />
      </b-form-group>

      <b-form-group
        id="input-group-3"
        label="Phone Number:"
        label-for="input-3"
      >
        <b-form-input
          id="input-3"
          v-model="form.number"
          placeholder="Enter phone number"
          required
        />
      </b-form-group>

      <b-form-group
        id="input-group-4"
        label="Date:"
        label-for="input-4"
      >
        <b-form-input
          id="input-4"
          v-model="form.date"
          placeholder="YYMMDD"
          required
        />
      </b-form-group>

      <b-button
        type="submit"
        variant="primary"
      >
        완료
      </b-button>
    </b-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        email: '',
        name: '',
        phone_number: '',
      },
      show: true,
    };
  },
  methods: {
    onSubmit(event) {
      event.preventDefault();
      alert(JSON.stringify(this.form));
    },
    onReset(event) {
      event.preventDefault();
      // Reset our form values
      this.form.email = '';
      this.form.name = '';
      this.form.food = null;
      this.form.checked = [];
      // Trick to reset/clear native browser form validation state
      this.show = false;
      this.$nextTick(() => {
        this.show = true;
      });
    },
  },
};
</script>
