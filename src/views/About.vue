<template>
  <div class="about">
    <h1>This is an about page</h1>
    <b-form-input v-model="text" placeholder="Enter your name"></b-form-input>
    <b-button v-b-modal.modal-1>Launch demo modal</b-button>

    <b-modal id="modal-1" title="BootstrapVue">
      <p class="my-4">{{text}}</p>
    </b-modal>
    <div class="mt-2">Value: {{ text }}{{selected}}</div>
    <b-form-group label="Individual radios">
      <b-form-radio v-model="selected" name="some-radios" value="A">Option A</b-form-radio>
      <b-form-radio v-model="selected" name="some-radios" value="B">Option B</b-form-radio>
    </b-form-group>
    <div class="mt-3">Selected: <strong>{{ selected }}</strong></div>
  </div>
</template>

<script>
import { Component, Vue } from 'vue-property-decorator';

@Component({})
export default class About extends Vue {
  text = '';

  selected = '';
}
</script>
